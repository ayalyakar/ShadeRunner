# DESIGN - Simulation Depth

## Decision

**DECIDED:** **Shallow — scripted world** at MVP. NPCs follow hand-authored routines; faction state updates on run outcomes and canonical events. No emergent faction warfare, no NPC-driven economy drift, no autonomous crowd simulation.

Deeper simulation (faction-vs-faction dynamics, economy drift per events, emergent gang conflicts) is **post-MVP**.

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
