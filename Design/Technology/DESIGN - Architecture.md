# DESIGN - Architecture

## Decision

**DECIDED:** Godot-native architecture with **autoload singletons** for cross-cutting services (save/load, event bus, clock, save state, faction state, audio manager), **scene-per-location** for walkable spaces, **scene-per-system** for Matrix / combat / dialogue overlays, and **Data/ YAML loaded at startup** as canonical source-of-truth. Simulation logic lives in GDScript; performance-critical hot paths can drop to C# / GDExtension if needed.

## Top-level repo structure

```
/
├── Design/                  # design docs (Markdown)
├── Data/                    # canonical lore, stats, content (YAML)
│   ├── Lore/
│   │   ├── Districts/
│   │   ├── Factions/
│   │   ├── NPCs/
│   │   └── Places/
│   ├── Systems/
│   │   ├── Magic/
│   │   ├── Matrix/
│   │   ├── Combat/
│   │   └── Progression/
│   ├── Gear/
│   │   ├── Weapons/
│   │   ├── Armor/
│   │   ├── Cyberware/
│   │   ├── BTL/
│   │   └── Drugs/
│   ├── Content/
│   │   ├── Scenes/
│   │   ├── Dialogue/
│   │   ├── Runs/
│   │   └── BTLChips/
│   └── Procgen/
│       ├── Names/
│       ├── AmbientBarks/
│       └── Appearance/
├── Sources/                 # sourcebook page screenshots (cited by Data/)
├── Media/                   # pre-ship art (Concepts/ Raw/ StyleRefs/ Prompts/)
├── Game/                    # Godot project
│   ├── project.godot
│   ├── assets/              # shipping art, audio, models
│   │   ├── art/
│   │   ├── audio/
│   │   ├── models/
│   │   └── animations/
│   ├── autoload/            # singletons
│   ├── scenes/              # .tscn files
│   ├── scripts/             # .gd (and .cs if used)
│   ├── ui/                  # UI scenes
│   └── addons/              # Godot plugins
└── Tools/                   # dev-time scripts (asset pipeline, Data validators)
```

## Godot project structure (`Game/`)

### Autoload singletons (order matters)

Loaded before any scene:

1. **`DataLib`** — loads all `Data/` YAML files at startup into typed in-memory tables. Provides query API (`DataLib.npc("James O'Malley")`, `DataLib.spell("Manabolt")`, etc.).
2. **`EventBus`** — global signal hub. Anything can emit / subscribe.
3. **`Clock`** — in-game time state (date, hour, minute). Ticks on downtime / scene actions. Emits signals on hour / day / month boundaries.
4. **`SaveGame`** — serialize / deserialize game state. Handles autosave / quicksave / manual slots / migrations.
5. **`WorldState`** — faction standing, per-NPC deltas, scripted event flags, per-venue flags. Persists via `SaveGame`.
6. **`Party`** — PC state (stats, inventory, contacts owned, romance state). Persists via `SaveGame`.
7. **`AudioManager`** — music / SFX / TTS playback with scene-profile mixing.
8. **`Input`** — keybind manager + remappable input layer.

### Scenes

- **`scenes/menu/`** — main menu, load game, chargen, options.
- **`scenes/world/`** — walkable 3D isometric scenes (one per location — neighborhood, venue, run-target interior).
- **`scenes/combat/`** — tactical combat instance (overlay / scene-swap from world scene).
- **`scenes/matrix/`** — Matrix minigame (overlay / scene-swap).
- **`scenes/dialogue/`** — dialogue overlay (portrait + text box).
- **`scenes/commlink/`** — diegetic hub UI.
- **`scenes/illustration/`** — 2D illustrated-scene player (story beats, NSFW scenes).
- **`scenes/chargen/`** — character creation flow.

### Scripts

- **`scripts/data/`** — YAML loader utilities, Data validators.
- **`scripts/simulation/`** — `FactionSim.gd`, `ClockSim.gd`, `AddictionSim.gd`, etc.
- **`scripts/combat/`** — initiative, dice resolver, damage pipeline, AI.
- **`scripts/matrix/`** — host nav, IC engagement, alert state.
- **`scripts/magic/`** — spell engine, summoning, drain.
- **`scripts/dialogue/`** — dialogue-tree runtime, skill-check evaluator.
- **`scripts/inventory/`** — weight / slot / equip rules.
- **`scripts/ui/`** — HUD, menus, tooltips.
- **`scripts/pc/`** — PC controller, karma spend, progression.
- **`scripts/npc/`** — NPC controller, schedule follower, dialogue trigger.

## Data loading

- **Startup:** `DataLib` loads all `Data/*.yaml` into memory. Total Data size budgeted small enough to hold in RAM at MVP.
- **Hot reload:** during development, `DataLib` watches Data/ for changes and re-loads (optional; dev-only).
- **Lookup API:** typed accessors — e.g. `DataLib.faction("Seattle Mafia") → FactionRecord`.
- **Missing / malformed data:** log-and-continue; game won't crash on bad YAML, but logs to console and a `DataErrors.log` for debugging.
- **Validation:** a `Tools/validate_data.py` script (or GDScript equivalent) walks every YAML and checks required fields, referential integrity (every NPC ref resolves, every source image exists), schema compliance.

## Event-driven simulation

- **World events** flow through `EventBus`. Run completion emits `run_completed` with payload; `WorldState` listens and applies faction / contact deltas; `Clock` listens and advances time; Trid feed listens and generates a headline.
- Scripts register listeners in `_ready()` / unregister in `_exit_tree()`.
- **Scripted hooks:** a run's YAML can declare `on_complete: [event_type]` entries — these are dispatched through `EventBus` on run completion.

## Dialogue system

- **Dialogue trees** live in `Data/Content/Dialogue/<npc-or-scene>.yaml`.
- Each node: speaker, text, portrait state, player options with tags (skill, faction, item required).
- **Runtime:** `DialogueRuntime.gd` interprets the tree, rolls skill checks, evaluates conditions, advances nodes.
- Templated variables resolve at node enter (`{{pc.name}}`, `{{last_event.rumor}}`).

## Combat system

- **`CombatController.gd`** orchestrates. Handles initiative queue, turn passes, action execution, resolution, state updates.
- **Attack pipeline:**
  ```
  Attacker declares action
    → gather dice pool (skill + attribute + mods)
    → gather TN (base + cover + range + wound + etc.)
    → roll exploding d6s
    → count successes
    → defender resists (opposed roll)
    → compute damage level delta
    → armor / resist check
    → apply damage to target's tracks
    → update wound penalty + status
    → broadcast result event
  ```
- **AI:** `EnemyAI.gd` per archetype. Utility-score actions per turn (self-heal, flank, shoot, retreat); pick highest.

## Matrix system

- Separate scene; activated when PC jacks in.
- **`MatrixController.gd`** tracks persona, host topology, IC presence, alert state.
- Meat body is paused in the world scene but vulnerable — world scene receives hostile-approach events and can trigger emergency jack-out.

## Magic system

- **`MagicController.gd`** handles spell casts, spirit summons, drain resolution. Calls into the combat pipeline for damage-dealing spells.
- Spirits are NPC-adjacent actors with their own statblock and AI.

## Save / load

- `SaveGame.serialize()` gathers state from all autoloads + current scene variables.
- `SaveGame.deserialize(save)` restores state, loads the saved scene, restores PC / NPC positions.
- **Scene-resumable state:** combat, dialogue, Matrix, illustrated scenes all support mid-scene save. Each system exposes `to_save()` / `from_save()` methods.

## Asset pipeline

- **3D models** (Meshy → Blender → glTF) land in `Game/assets/models/`.
- **2D art** (local SDXL → curated) lands in `Game/assets/art/`.
- **Audio** (Piper / XTTS / ElevenLabs / SFX) lands in `Game/assets/audio/`.
- `Tools/` scripts automate batch generation where useful (batch TTS from dialogue YAML, batch portrait gen from NPC list, batch model cleanup from Meshy exports).

## Performance targets

- **60 FPS** at 1080p on mid-range Windows hardware.
- **Scene load:** under 3 seconds.
- **Save / load:** under 2 seconds.
- **Memory:** RAM usage under ~2 GB MVP; VRAM under ~4 GB.

## Testing

- **GDScript unit tests** via gut (Godot's unit test framework). Covers dice resolver, damage pipeline, economy math, addiction ticks, save/load round-trip.
- **Data validation** in CI (if any CI is set up) or in a pre-commit hook.
- **Playtest scripts** for scripted run-through validation (automate the MVP run to detect regressions).

## Dependency / module policy

- **Prefer Godot-native** over external libraries.
- **Small, focused GDScript modules.** No monolithic controllers.
- **Typed GDScript** where it helps readability and tooling.
- **C# / GDExtension** escape hatch for perf-critical systems only.

## Open questions

- Godot 4.x minor version pin (latest stable at project start).
- Monorepo vs. split repo (Design / Data / Game) — currently monorepo, flag for re-evaluation if repo gets huge.
- CI setup — personal project, probably not needed at MVP; a local pre-commit hook can do data validation.
- Hot-reload Data in editor — nice-to-have.
- Mod-loader seed — even with modding post-MVP, keep file paths stable so future mod paths don't break.
- Scene-swap vs. scene-overlay for combat / Matrix — committed to overlay-style sub-scenes where possible for instant transition.
- State-machine pattern for scene / combat flow — formalize one pattern across systems.
