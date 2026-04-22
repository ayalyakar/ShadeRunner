# DESIGN - Simulation Depth

## Decision

**DECIDED:** Hybrid between **Dwarf Fortress / RimWorld** (deep per-agent sim) and **Gothic / Kingdom Come: Deliverance** (named NPCs with real routines and relationships, ambient crowds). Active zone runs deep; distant zones run abstracted (see `Technology/DESIGN - Persistence.md`).

## Per-NPC data (named NPCs)

- **Identity:** name, metatype, age, SIN tier, appearance.
- **Role:** profession, affiliations, income, lifestyle tier.
- **Schedule:** weekly routine (work, sleep, meals, hobbies, patrols).
- **Goals:** short-term needs, mid-term aims, long-term ambitions.
- **Relationships:** named edges to other NPCs (family, lovers, rivals, owed favors).
- **Memory:** what they remember about the player and significant events.
- **Inventory:** what they own/carry relevant to play.
- **Traits:** personality axes that bias decisions.

## Ambient crowds

- Statistical populations rather than individual agents in high-density scenes.
- Summoned into concrete agents only when the player interacts.
- Once interacted with, promoted to minor-NPC status with generated persistent identity.

## Autonomous behavior

NPCs independently:
- Follow schedules (with improv on interruptions).
- Pursue goals (apply for jobs, break up, move apartment, join a gang).
- React to events (mourn the dead, flee riots, upgrade gear after a raise).
- Spread rumors through social graph edges (player's rep propagates).

## Economy, factions, and world events

Simulated in parallel — see `World/DESIGN - Factions.md` and `World/DESIGN - Economy.md`. They drive NPC-visible change (prices, hiring, turf wars, corp sweeps).

## Performance envelope

- Target: active zone with ~1,000 named NPCs ticking at 1 Hz comfortably.
- Far zones: aggregate only, ~10 sprawl-level stats per zone updated per in-game hour.
- Promotion/demotion of zones happens off-thread to avoid hitches.
- See `Technology/DESIGN - Engine.md` on custom modules for the sim kernel.

## Open questions

- How many "named" NPCs per district is sustainable vs. useful?
- How to stop the sim from grinding on a single goal for ages (stuckness patterns).
- Rumors and memory decay: how fast does an NPC forget?
- Cross-zone knowledge: does Tacoma know about a Redmond event, and through what channel?
