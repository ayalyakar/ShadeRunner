# DESIGN - Simulation Depth

## Decision

**DECIDED (MVP):** **Shallow — scripted world** at MVP. NPCs follow hand-authored routines; faction state updates on run outcomes and canonical events. No emergent faction warfare, no NPC-driven economy drift, no autonomous crowd simulation.

**DECIDED (post-MVP ambition):** The long-term target is **deep, realistic, complex simulation** in the RimWorld / Dwarf Fortress register — applied to faction dynamics, economy drift, NPC schedules, crime emergence, and weather / environmental effects. MVP is the scripted seed; the simulation layer is the game the seed grows into.

The project accepts this is ambitious for solo scope, and mitigates it by: (1) locking MVP to scripted depth, (2) designing data records forward-compatible with simulation (e.g. faction standing already lives as numeric data, not dialogue flags), (3) building simulation modules incrementally post-MVP rather than all-at-once.

### Forward compatibility rules

Even at MVP, all content is authored as if it will eventually feed a simulation:

- Factions have numeric standing, not just flags.
- NPCs have schedules, bribe profiles, and relationship graphs — even if MVP only uses a subset.
- Economy has real prices and real cadences, even if MVP only advances a few of them.
- Weather / smog / rain events are state-tracked, not visual-only, even if MVP only uses them for scripted scenes.

This is the "author forward" discipline that lets post-MVP simulation land without canonical retrofitting.

## What MVP-shallow means

### NPCs
- **Named NPCs** have hand-authored schedules (morning venue, afternoon venue, evening venue, sleep location).
- **Ambient crowd** is procgen-seeded but non-interactive (doesn't schedule; spawns on zone entry; doesn't remember the PC).
- **Named NPCs remember** the PC — dialogue and attitude reflect past interactions (runs, romance, violence witnessed, favors owed).

### Factions
- **State lives in `Data/`** as per-faction standing fields updated by scripted events.
- **Scripted triggers only.** A run affects faction state via scripted consequences — not simulated resource drain or autonomous retaliation.
- **Faction relationships** are static relationship graphs at MVP (Mafia vs. Yakuza, Humanis vs. metahumans, Lone Star vs. everyone). Scripted event hooks can modify these.

### Economy
- **Shop inventories** refresh on a cadence (e.g. weekly stock roll). Prices are authored; no supply-demand simulation.
- **Run payouts** are authored per-run; no market-driven tiering.

### Time
- **Real clock minutes** (see `DESIGN - Time.md`). Hours / days / weeks pass visibly; NPCs exist at their scheduled location at clock time.
- **Downtime actions** advance the clock (training, sleeping, visiting contacts).

### Events
- **Run outcomes** fire scripted consequences: faction rep adjustments, new dialogue, contact reactions, occasional retaliation scenes.
- **Canonical era events** (Crash 2.0, etc. — post-MVP) are scripted inserts, not emergent.

## What's out at MVP

- **Autonomous NPC decision-making** across scenes.
- **Faction warfare simulation** (turf wars running in the background).
- **Economic drift** (prices shifting with in-world supply / demand).
- **Random NPC crime / emergencies** (muggings, shootings) in ambient scenes.
- **Dynamic weather** (weather is a scripted / scene-level feature, not a simulation).
- **Ecological simulation** (gang respawn, population refresh from demographics).

## Post-MVP trajectory

Simulation depth increases in layered passes after MVP:

1. **Scripted faction events** that fire on time-of-day triggers or rep thresholds (hate-crime ambient, gang turf scuffles, Humanis rallies).
2. **Shop inventory drift** responsive to faction state (Yakuza-controlled shops quality goes up in Yakuza-ascendant districts).
3. **Faction-vs-faction skirmishes** the PC can witness or interrupt.
4. **Procgen ambient incidents** (muggings, drug deals, gang fights) in Barrens zones.
5. **Autonomous named-NPC daily life** (contacts evolve their venues, relationships drift).

## Pipeline

- Faction standing: `Data/Lore/Factions/<faction>.yaml` — standing field gets updated via save-game deltas.
- NPC schedules: `Data/Lore/NPCs/<name>.yaml` — `schedule:` block declares hand-authored location per time slot.
- Scripted event hooks: `Data/Events/<event>.yaml` — trigger conditions, consequences.

## Open questions

- Scripted-event author workload — what's the content budget per run?
- Do any factions have "living" state at MVP (even scripted), or is everything a consequence-of-PC-action?
- How visible is the simulation to the player? (Always-on news ticker? Faction dashboard? Dialogue-only?)
- Does weather matter at all at MVP, or is it post-MVP flavor?
