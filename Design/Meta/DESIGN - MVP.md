# DESIGN - MVP

## Decision

**DECIDED:** The MVP is one district, one archetype, one run type:

- **District:** Redmond Barrens.
- **Archetype:** Street samurai (physical combat; also covers physical adept with minor tweaks).
- **Run type:** A single, specific run structure (framed below).

The MVP is **shippable to self**: complete end-to-end, no placeholders in the critical path.

## Why these choices

- **Redmond Barrens:** classic SR starting territory, gang-heavy, lawless, gives meaningful diversity of encounters without corp-tier security.
- **Street samurai:** validates combat (the hardest system to get right) first. Matrix, magic, rigging stubbed for later.
- **One run type:** forces a complete vertical slice instead of broad shallow coverage.

## MVP scope — what's in

- Chargen: point-buy karma, Core 5 metatypes, street-sam-viable skills / gear only.
- A single Redmond Barrens neighborhood hand-built, walkable in first-person and isometric.
- Combat: phase-pass turn-based, free-move, dice-pool engine, one weapon type (e.g. SMG) and one melee type.
- One Johnson, one fixer, one contact archetype: meet the Johnson, take the job.
- Run structure: Meet → Legwork (light) → Execution → Payout.
- Lifestyle: one Squatter / Low tier with monthly rent due.
- Day / night clock.
- Save anywhere (no ironman yet).
- Basic heat tracking.
- Basic reputation tracking (street cred increment on success).
- Minimal UI: character sheet + combat HUD + commlink notifications.

## MVP scope — what's explicitly out

- Magic, Matrix, rigging subsystems (all stubbed or skill-gated out).
- Other metatypes beyond Human + Ork (optional: add Elf).
- Multi-district.
- Era transitions (MVP stays in a fixed year).
- NPC schedules at scale (MVP uses simple routines for ~20 named NPCs).
- Romance / contacts beyond the minimum two.
- Procgen side runs.
- 2D painted cutscenes (placeholder panels only).
- Full voice acting (TTS placeholder).
- Investigation case-board (one lightweight scripted run).

## Acceptance criteria

1. Start new game → chargen → wake up in Redmond Barrens.
2. Receive a fixer call → attend Johnson meet → accept a run.
3. Do minimal legwork (one dialogue scene, one Perception check).
4. Execute the run end-to-end (stealth or combat path, both viable).
5. Collect payout, gain karma and street cred.
6. Return to safehouse, time advances, rent bill approaches.
7. Save, quit, reload — all state preserved.

If any step breaks, the MVP is not done.

## Post-MVP priorities (order TBD)

1. **Matrix subsystem v1** — integrate decker contacts and security-bypass puzzles.
2. **Magic subsystem v1** — add awakened archetype (adept first, mage second).
3. **Rigging subsystem v1** — basic drone jump-in.
4. **Second district** — open up another Seattle neighborhood.
5. **NPC simulation v2** — scale named NPC count and schedule fidelity.
6. **Era transitions** — ship 2050 → 2064 including Crash 2.0 event.

Which of 1–3 comes first is an **open question** (see `Design/DESIGN - Production.md`).

## Open questions

- Exact acceptance test for "feels like Shadowrun" — define metrics or trust playtest?
- How much polish before declaring MVP done (perfectionism risk).
- Should the MVP have any single save preserved for future content as a legacy save format?
- Is there any value in a pre-MVP "tech demo" (combat-only prototype) to validate Godot + custom modules earlier?
