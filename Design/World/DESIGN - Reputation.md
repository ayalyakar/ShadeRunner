# DESIGN - Reputation

## Decision

**DECIDED:** Reputation is **multi-layered, persistent, and propagated through a social graph**. Four layers run in parallel:

1. **Persistent consequence** — killed contacts stay dead; toppled gangs don't respawn; corp actions reshape districts.
2. **Emergent faction shifts** — factions fight, absorb, or collapse independently of the player; the player can nudge outcomes.
3. **Personal reputation web** — named NPCs remember; reputation spreads via social graph edges.
4. **Environmental / tech progression** — decades-long rises in wireless use, AR, new cyberware generations that change the baseline.

## Personal reputation mechanics

- **Street Cred:** how respected the runner is in the shadows.
- **Notoriety:** how infamous / dangerous the runner is perceived as.
- **Public Awareness:** how visible the runner is to the wider world (very bad for a shadowrunner).
- Per-faction **Standing** (scalar + history).
- Per-contact **Loyalty & Connection** (see `Social/DESIGN - Contacts.md`).

## Propagation model

When a reputation-changing event happens:
- The affected NPC(s) record it in their memory.
- Event is gossiped through social graph edges with a **decay** per hop and per unit of time.
- Some events are **loud** (public murder → fast wide spread); others are **quiet** (a favor well done → slow narrow spread).
- Public Awareness is a one-way ratchet that mostly goes up.

## Faction-level persistence

- Kills, betrayals, and services to a faction are logged and influence future job offers, pricing, and hostility checks.
- Factions can **blacklist** a runner, **hire** them preferentially, or **hunt** them.
- A faction's overall fortunes (share of a district, money, manpower) are tracked; the player's cumulative influence counts.

## Tech-era progression

- Wireless/commlink adoption curve from the SR1 era (rare) to SR5 (ubiquitous).
- Cyberware generations come to market; older models become cheap; essence costs shift.
- Gear, programs, spells introduced / deprecated per era.
- The world visibly modernizes (or decays) around a long-lived PC.

## Open questions

- How to display reputation to the player without making it a spreadsheet.
- Memory retention rates — how long does a random gang mook remember that the PC once spared them?
- "Forgiveness" mechanics — can reputation ever be rebuilt, and through what labor?
- Anonymity: can the PC cultivate multiple street identities with separate rep webs?
