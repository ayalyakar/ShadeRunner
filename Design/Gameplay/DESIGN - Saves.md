# DESIGN - Saves

## Decision

**DECIDED:** **Free manual saves anywhere** as the default. Ironman (single save, no save-scum) is an opt-in toggle per character (see `Gameplay/DESIGN - Difficulty.md`).

## Save model

- **Quick save** — one slot, hotkey bound.
- **Manual saves** — unlimited named slots.
- **Auto-saves** — on zone transitions, run phase transitions, before high-risk events.
- **Backup rolling saves** — N-deep rolling auto to prevent corruption loss.

All saves use the persistence model in `Technology/DESIGN - Persistence.md` (event log + zonal snapshots), which keeps write costs low.

## Save contents

Every save is a complete, standalone world state:
- World seed and event log pointer.
- Zonal snapshots.
- Player state (PC sheet, inventory, relationships, current scene).
- Meta (version, timestamp, playtime, character id).

## Ironman mode

- Single save per character.
- Quicksave and manual saves disabled.
- Auto-saves only, at pre-defined scheduled points.
- Death or run failure cannot be reverted.
- Character survives via `Character/DESIGN - Aging.md` protagonist-switch rules if enabled.

## Load behavior

- Normal save: reload restores the exact world state.
- Ironman: "reload" simply re-reads the current single save; no time-travel.

## Run-failure handling

Graduated per `Design/DESIGN - Vision.md`:

- Most runs: failure = consequence cascade (heat, debt, injury, rep loss), not death.
- Some "deniable asset" runs: lethal by design; failure can end the PC.
- Ironman: all deaths are permanent.

Non-ironman players can save-scum these lethal runs; ironman players must accept the outcome.

## Open questions

- Save size target — event log size growth over decades.
- Cloud save support — probably not for a personal project.
- Save naming and metadata display.
- Crash-safety: atomic writes and corruption recovery.
