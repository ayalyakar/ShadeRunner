# DESIGN - Persistence

## Decision

**DECIDED:** Save state is a single serialized document containing all runtime variables (PC, world, factions, contacts, inventory, clock, scene). **Save-anywhere** UX (see `Gameplay/DESIGN - Core Loop.md`). Save format: Godot's native resource serialization (binary / JSON-ish), with manual-slot saves, autosave, and quicksave.

## Save content

Every save includes:

### PC state
- Attributes (current + any temp mods), skills, karma balance, karma earned lifetime.
- Essence, Magic rating effective.
- Cyberware installed.
- Spells known / programs loaded / adept powers.
- Nuyen, favors owed / owed-to.
- Reputation (per-faction).
- Health state (Physical + Stun track current boxes filled, wound penalties).
- Addiction state (per substance: tolerance, addiction tier, last use).
- Active status effects (sustained spells, drug buffs, fatigue).

### Inventory
- Carried items (weight tracked).
- Home-stash items.
- Equipped slots.
- Ammunition per weapon.

### Contacts
- Per-contact: Loyalty, current venue, last-contact timestamp, any in-progress trust beats, romance-arc state.

### World
- **Clock:** exact in-game date + time.
- **District state:** any flagged events fired, scripted faction deltas applied.
- **NPC state:** schedule overrides, alive/dead, relationship deltas.
- **Venue state:** flags (discovered, unlocked, owned, compromised).
- **Active run state:** if mid-run, all run-level variables (phase, objectives completed, intel gathered, kills logged).
- **Matrix state:** any mid-run Matrix session state.
- **Weather / time-of-day derived.**

### Engine state
- Current scene ID + camera / PC position.
- Pending scripted events (queued triggers).
- UI state (tooltips seen, journal entries).

### Settings (separate from save)
- Audio mix, text scale, subtitle opacity, keybind profile. Lives in `user://settings.cfg`, not per-save.

## Save format

- **Godot `ResourceSaver`** with a custom Resource subclass (`SaveGame`) holding nested `Resource` instances per domain (PC, World, Factions, etc.).
- **Binary format at ship** (compact, fast); **JSON fallback** during dev for inspection.
- **Version field** in every save; load path applies migrations if version mismatches.

### Schema versioning
- `save_version:` integer incremented on any schema change.
- Migration functions per upgrade step. Old saves upgrade on load.
- During dev: breaking saves is fine (flag in README / release notes). Post-MVP: migrations mandatory.

## Save UX

- **Manual save slots:** unlimited; labeled with timestamp, PC name, in-game date, scene location.
- **Autosave:** on run-start, on run-end, on lifestyle-change events (rent paid / missed), on death-avoidance events.
- **Quicksave / quickload:** one dedicated slot, F5 / F9 convention.
- **Ironman:** **not supported** per project decision (save-anywhere).
- **Save preview thumbnail:** a screenshot of the current scene, stored alongside the save record.

## Savepoint restrictions

- **Combat:** saveable mid-combat? Yes at MVP (save-anywhere policy).
- **Matrix:** saveable mid-Matrix? Yes; jacks-in state serializes.
- **Dialogue:** saveable mid-dialogue? Yes, at the current node.
- **NSFW scenes:** saveable mid-scene? Yes. Scene resume restores exact position.

## Cloud / sync

- **Out of scope.** Local saves only at MVP.

## Screenshots / export

- **Photo mode / export:** out of scope at MVP.

## Deterministic replay

- RNG state seeded from save state where practical — so load restores identical outcomes for in-progress actions (attack rolls, dice chains, crowd spawning).
- **Non-goal:** exact replayability of full runs. Just "reload brings you back to the same state you left."

## Storage location

- **Saves:** `user://saves/<slot>.res` (or `.save`), Godot's user data dir.
- **Settings:** `user://settings.cfg`.
- **Screenshots for save previews:** `user://saves/<slot>.png`.

## MVP scope

- Single save format + version 1.
- Manual slots + autosave + quicksave.
- Save-anywhere enforced.
- Settings persisted separately.
- No cloud, no photo mode, no ironman.

## Open questions

- Exact binary vs. JSON save tradeoff — binary for ship, JSON during dev, or always both (JSON + binary side-by-side for debugging)?
- Save-file size budget — any concerns with large world state?
- Save-corruption handling — prompt on load failure, auto-fall-back to previous slot?
- Cheat-save editing — personal project, likely fine to leave saves editable (bonus for modding-adjacent tinkering).
- Mid-scene save fidelity for complex scenes (NSFW scenes with reactive state) — any edge cases where resume fails gracefully?
- Export / import saves across machines — zip of user data directory for now, or a dedicated export UI?
- Save NSFW scene checkpoints specifically — does scene-skip count as "played"? (For romance-arc state tracking.)
