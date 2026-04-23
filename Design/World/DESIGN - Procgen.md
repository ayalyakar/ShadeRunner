# DESIGN - Procgen

## Decision

**DECIDED:** **Hand-authored core at MVP.** The main run, the hand-built Redmond neighborhood, named NPCs, key contacts, and the romance arc are all authored content. Procgen is **out of MVP**, slotted for post-MVP expansion.

## What's hand-authored at MVP

- The single MVP run (Retrieval job from the Corporate Mr. Johnson).
- The MVP Redmond neighborhood (full layout, buildings, NPC placements, ambient dialogue triggers).
- All named NPCs (fixer, Johnson, romance contact, street doc, a handful of flavor NPCs).
- Contact dialogue and romance arc.
- NSFW scenes (one vertical-slice illustrated scene minimum).
- BTL chip library (small hand-authored set).

## What's procgen-seeded at MVP (crowd-level only)

**Ambient crowds only.** Streets and venues populate with crowd NPCs that are procgen-sampled from district demographics:

- Metatype mix from `Data/Lore/Districts/<district>.yaml` `metatype_mix`.
- Clothing / appearance pulls from Meshy-generated asset pools.
- Names pulled from per-metatype name tables.
- Crowd NPCs are non-interactive — you can't engage them in dialogue. They animate, speak ambient barks, react to combat proximity, and despawn when the scene clears.

## What's deferred to post-MVP

- **Procgen side runs.** Templated run generation (target / Johnson / location / complication / twist).
- **Procgen dialogue variants.** Runtime template-substitution for minor-NPC dialogue.
- **Procgen item variants.** Modifiers and quality tiers on gear.
- **Procgen faction events.** Ambient hate-crimes, turf skirmishes, gang raids populated on a timer.
- **Procgen BTL / drug content.** Auto-generated chip and drug flavor text for minor chips.
- **Fully procgen districts.** Far post-MVP, if ever.

## Procgen pipelines (when they land)

### Crowd-seed (MVP)
```
Zone entry
  → roll crowd size from venue/time-of-day
  → for each slot: sample metatype per district mix
    → pull appearance kit from Meshy pool
    → pull name from table
    → pull ambient bark set per metatype / district / time
```

### Templated side-runs (post-MVP)
```
Run template  +  Johnson archetype  +  target  +  complication
  → drafts filled with LLM at dev time (curated library of variants)
  → committed to Data/Runs/SideRuns/
  → runtime just loads a pre-generated variant; no runtime LLM
```

This matches the project-wide rule: **no runtime LLM** (see `Technology/DESIGN - AI Tooling.md`).

## Rules for procgen

- **Neighborhood-level metahuman clustering** — even ambient-crowd procgen should respect the SR canon that metahumans cluster for self-defense post-Night of Rage. Redmond demographic rolls differ between Touristville neighborhoods and Plastic Jungles. Enforced at the sub-area level, not the district level.
- **Procgen NEVER produces protected content.** Minor-age NPCs never appear in sexual contexts. Procgen pipelines carry hard filters against any such output; the filter is model-independent.
- **Procgen assets are committed.** Once a procgen output is used (e.g. a generated crowd kit), it's committed to Git so the game is deterministic across machines.

## Namefiles / tables

Committed data tables that procgen pulls from:

- `Data/Procgen/Names/<metatype>-<gender>-<culture>.yaml` — first-name / last-name tables.
- `Data/Procgen/AmbientBarks/<context>.yaml` — bark libraries (PC-adjacent, combat-adjacent, idle, weather, NSFW-venue, drug-den, etc.).
- `Data/Procgen/Appearance/<metatype>-<tier>.yaml` — clothing / cyberware-visibility / vibe presets.

## Deterministic replay

- Procgen uses **seeded RNG** keyed to save-game state + scene ID. Same save + scene = same crowd.
- Respects the "no runtime LLM" rule — everything is lookup + RNG.

## Open questions

- How many name entries per table before procgen crowds feel stale?
- Does the player ever get to promote a crowd NPC to a named NPC (dialogue escalation hook)?
- BTL chip procgen — generate variant chips from a library, or hand-author all MVP chips?
- Ambient-bark cross-talk — do crowd NPCs ever talk to each other, or just to nobody?
- Crowd density tuning — Seattle feels dead with too few, busy with many, laggy with a lot.
