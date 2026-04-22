# DESIGN - Difficulty

## Decision

**DECIDED:** Two mechanisms, combined:

1. **Tunable difficulty sliders** — independent axes the player can adjust.
2. **Hardcore / ironman mode** — single save, no save-scum, permadeath enabled.

No "story mode" that disables lethality; no full accessibility suite yet (may revisit).

## Slider axes (initial)

- **Combat lethality** — damage taken multiplier, dodge/parry thresholds.
- **Economy pressure** — lifestyle costs, payouts, black-market markups.
- **Heat** — how quickly law / corp attention accumulates.
- **Sim harshness** — NPC predation (gang muggings, corp sweeps), illness frequency.
- **Essence / cyberware risk** — chance of complications, rejection frequency.
- **Clock** — fast-forward ease, interrupt frequency.

Each slider has presets (Chill / Default / Brutal) plus free tuning.

## Hardcore / ironman mode

- Single save per character.
- Save only on quit and on scheduled auto-save points (safehouse, chapter transitions).
- No reload to a pre-death state; death or run failure is permanent.
- Some achievement / completion flag; optional.

See `Gameplay/DESIGN - Saves.md` for how this interacts with the free-save default.

## Accessibility (minimal for now)

- Subtitles for all voiced dialogue.
- Remappable keys.
- Colorblind-safe palette as the default art direction.
- Font size scaling.

Full suite (dyslexia fonts, TTS narration, motor assists, audio-cue mode) is **deferred, not refused**. Revisit once MVP is playable.

## Defaults

- Default difficulty = "Default" across all sliders.
- Default save = free manual saves (see `Gameplay/DESIGN - Saves.md`).
- Hardcore is an explicit opt-in per character.

## Open questions

- Should a "Shadowrun-authentic" preset exist that mirrors tabletop harshness?
- Can difficulty be changed mid-game, or is it locked at character creation?
- Should hardcore have any mechanical reward beyond pride?
- Does the sim behave differently under different sliders, or just the player-facing numbers?
