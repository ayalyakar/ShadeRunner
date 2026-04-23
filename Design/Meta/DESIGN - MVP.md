# DESIGN - MVP

## Decision

**DECIDED:** MVP is a **full-run vertical slice** — Meet → Legwork → Execute → Payout, end-to-end, for any of the four playable archetypes, in **Redmond**.

MVP is **shippable to self**: no placeholders in the critical path. A missing feature means the feature is out of MVP; a present feature means it works.

## Scope

### District
- **Redmond only.** One hand-built neighborhood walkable in isometric 3D. Exact neighborhood TBD (candidates: a Touristville neighborhood or a Redmond Barrens sub-area; decided once Redmond pages are ingested).
- Other Seattle districts exist as canonical `Data/` stubs only; not visitable.

### Archetypes (all four playable at MVP)
- **Street Samurai** — combat archetype. Built first (the combat engine is the highest-risk subsystem).
- **Physical Adept** — magical combat; reuses combat scaffolding with a magic overlay.
- **Decker** — Matrix archetype. Requires Matrix subsystem at MVP depth.
- **Full Mage / Shaman** — spellcasting. Requires Magic subsystem at MVP depth.

Each archetype has **one MVP-playable build** — not the full skill/spell/program tree. More builds land post-MVP.

### Chargen
- Blank-slate character creation: metatype, archetype, primary stats, skills, starting gear, backstory beats.
- Metatypes at MVP: Human, Elf, Ork, Dwarf, Troll (five core SR metatypes).
- Chargen is point-buy against karma (SR1E-ish economy).

### Run structure
- **Meet** — fixer-to-Johnson in a Redmond venue (bar / hotel / safe house).
- **Legwork** — at least one dialogue-skill beat and one perception / data-search beat.
- **Execute** — mission environment. Must be completable via combat *or* non-combat path, with at least one branch (stealth / hack / magic / social).
- **Payout** — dialogue, karma, rep, nuyen. Consequence imprinted on faction / contact state.

### Systems MVP depth
- **Combat:** turn-based phase/initiative, dice-pool resolution, SR-correct drain/recoil/armor math, one melee + one ranged archetype weapon, cover, line-of-sight.
- **Matrix:** one decking loop — a host, IC opposition, file retrieval or node control action, jack-out consequences.
- **Magic:** one spell (combat), one conjuring (spirit summons), drain resolution, line-of-sight, spirit services.
- **Rigging:** **NOT in MVP.** Deferred post-MVP. A playable Rigger is post-MVP.
- **Social / contacts:** one fixer, one Johnson, one contact archetype (e.g. fence), dialogue with skill checks.
- **Economy:** monthly rent at Low tier (2,000¥/mo per prior anchor), payout → karma / rep / nuyen loop.
- **NSFW:** at minimum, one illustrated-explicit scene in the vertical slice (e.g. a brothel / BTL studio encounter as an optional Legwork path). Validates the NSFW pipeline end-to-end.

### Presentation / UI
- Isometric 3D with fixed camera.
- Character sheet, combat HUD, dialogue UI, commlink notifications.
- Save-anywhere.
- Day/night clock.

### Out of MVP scope
- Rigging.
- Multi-district travel.
- Era transitions (2050 fixed at MVP).
- Multiple MVP runs (single run; procgen runs are post-MVP).
- Full voice acting (TTS / text-only at MVP).
- Beyond-core metatypes (shapeshifters, drakes, etc.).
- Companion control in combat.
- Cutscene cinematics.

## Why these choices

- **Redmond:** classic SR starting ground, deep canon baggage, lawless Barrens → plenty of run content; the prior pass established it as anchor.
- **All four archetypes at MVP:** the project's fantasy is "Shadowrun", and Shadowrun isn't one archetype. Accepting the cost.
- **Street Sam first:** combat is the highest-risk subsystem. Validate it with the simplest archetype, then plug magic/Matrix onto the scaffolding.
- **One run:** forces a complete vertical slice instead of broad shallow coverage.
- **NSFW in vertical slice:** NSFW is a stated pillar, so it must survive MVP end-to-end, not be promised for later.

## Acceptance criteria

1. Start new game → chargen (any of four archetypes) → wake up in Redmond.
2. Receive a fixer call → Johnson meet → accept a run.
3. Legwork beat (dialogue + perception + optional NSFW venue).
4. Execute the run end-to-end via at least two different archetype paths (combat and one other).
5. Payout; karma, rep, nuyen applied.
6. Rent clock advances; save, quit, reload preserves state.
7. NSFW pipeline has at least one illustrated-explicit scene hooked in and working.

## Post-MVP priorities

1. **Rigging subsystem v1.**
2. **Additional Redmond neighborhoods.**
3. **Second district opened (Downtown or Tacoma).**
4. **Procgen side runs.**
5. **Era-transition system (2050 → 2064).**
6. **Deeper NSFW pipeline (romance arcs, brothel hub, BTL studio runs).**
7. **Companion-in-combat control.**

## Open questions

- Which Redmond neighborhood is hand-built? Picked once Redmond pages are ingested.
- First run type (retrieval / protection / extraction / sabotage / NSFW-primary)?
- Magic tradition coverage at MVP (hermetic + shamanic only, or all published)?
- Matrix archetype viability in MVP depth — is one decking loop enough to make Decker feel distinct?
- NSFW scene placement in the vertical slice — optional Legwork side path, or mandatory?
