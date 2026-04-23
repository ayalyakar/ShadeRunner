# DESIGN - Architecture

## High-level shape

The game is a **simulation kernel** wrapped in **perspective-specific presentation layers**. The sim owns truth; the views render it.

```
+----------------------------------------------------+
|  Perspectives (swap per context)                   |
|  - Isometric tactical (runs, combat)               |
|  - First-person immersive (exploration, stealth)   |
|  - Terminal / text (Matrix deep dive)              |
|  - 2D painted panels (cutscenes, narrative beats)  |
+----------------------------------------------------+
|  Game Services (queries/commands)                  |
|  - Combat, Matrix, Magic, Rigging, Social, Sim     |
+----------------------------------------------------+
|  World State (single source of truth)              |
|  - Entities, components, event log, indexes        |
+----------------------------------------------------+
|  Simulation Kernel (ticks world forward)           |
|  - NPC AI, economy, factions, time, tech progress  |
+----------------------------------------------------+
```

## Guiding principles

- **One world, many lenses.** The player sees the same world through different cameras/UIs; no parallel simulations.
- **Event-sourced world state.** Every consequential change is an event. Enables replay, debugging, save diffs, and reputation propagation.
- **Deterministic given seed + event log.** Reproducibility is a debugging superpower for a solo dev.
- **Time is explicit.** Every tick advances by a declared delta; nothing in the sim uses wall-clock.
- **Zoned simulation.** Near the player: high-fidelity ticks. Far from the player: coarse abstractions. See `Technology/DESIGN - Persistence.md`.

## Perspective switching

Entering a Matrix deep dive, going Astral, jumping into a drone — each swaps the **view** and the **active control scheme**, not the underlying world. A player's meat body, Astral projection, and jumped-in drone all exist as entities in the same world; the camera follows the currently-possessed one.

## Module boundaries (draft)

- `core/` — world, entities, events, time.
- `sim/` — NPC AI, faction logic, economy, tech-era rules.
- `systems/` — combat, matrix, magic, rigging, social resolvers.
- `content/` — data-driven descriptions of gear, spells, programs, NPCs.
- `views/` — scenes/scripts for each perspective.
- `ui/` — context-dependent UI layers (see `Presentation/DESIGN - UI.md`).
- `tools/` — content pipeline (LLM-assisted authoring, procgen templates).

## Open questions

- Event store: SQLite? Custom binary? Godot Resource packs?
- ECS or plain classes? (Leaning Godot's node model with a thin component layer for sim entities.)
- Single-process sim or separate sim server? Probably single-process until profiling says otherwise.
- Scripting for designer-authored content (quests, dialogue trees): embedded DSL vs JSON/YAML vs GDScript callables.
