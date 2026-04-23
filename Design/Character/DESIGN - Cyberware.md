# DESIGN - Cyberware

## Decision

**DECIDED:** MVP ships a **minimal starter cyberware kit** covering each archetype's critical needs. Full SR1E cyberware catalogue is post-MVP. Every piece costs nuyen *and* Essence; Essence loss degrades Magic rating for Awakened characters.

## Essence economy

- Starting Essence: **6.0** for all metatypes (humans canonical; metatypes use same starting Essence in MVP).
- Each piece of cyberware has an Essence cost (fraction or whole).
- Essence cannot go below 0 — that kills the character.
- **Magic rating** equals `Magic attribute - (6 - current Essence)`. Adepts and mages lose Magic as Essence drops. A Magic 6 character with 4.5 Essence has effective Magic 4.
- Bioware (post-MVP) uses a parallel "bio-index" that has a lower multiplier against Magic.

## MVP catalogue

All items are available at chargen (via nuyen) or post-chargen from a street doc. Prices and Essence costs are indicative SR1E-ish; final numbers pegged to MVP economy calibration.

### Combat / reflex
| Item | Essence | Nuyen | Effect |
|---|---|---|---|
| **Wired Reflexes 1** | 2.0 | 55,000¥ | +1 Reaction · +1 Initiative Pass |
| **Wired Reflexes 2** | 3.0 | 165,000¥ | +2 Reaction · +2 Initiative Passes |
| **Muscle Replacement 1** | 1.0 | 30,000¥ | +1 Strength · +1 Agility |
| **Dermal Plating 1** | 0.5 | 4,000¥ | +1 Ballistic / Impact armor |
| **Bone Lacing (aluminum)** | 0.5 | 12,000¥ | +1 Body track (Physical damage resistance) |

### Senses
| Item | Essence | Nuyen | Effect |
|---|---|---|---|
| **Cybereyes** (basic) | 0.2 | 4,000¥ | Socket for eye-mods |
| **Flare Compensation** | 0.1 | 1,000¥ | Negates flare penalties |
| **Low-light Vision** | 0.2 | 2,000¥ | See in low light without penalty |
| **Thermographic Vision** | 0.2 | 2,000¥ | See body heat (through walls at short range) |
| **Smartlink (v1)** | 0.5 | 3,500¥ | +2 dice on Firearms with a smart-linked weapon |
| **Cyberears** (basic) | 0.2 | 3,500¥ | Socket for ear-mods |
| **High-frequency Hearing** | 0.1 | 1,500¥ | Detect cyber / electronic signals by sound |
| **Sound Dampener** | 0.1 | 800¥ | No deafening from gunfire / flashbangs |

### Matrix / comms
| Item | Essence | Nuyen | Effect |
|---|---|---|---|
| **Datajack** | 0.2 | 1,000¥ | Required for cyberdecking |
| **Headware Memory** (100 MP) | 0.1 | 500¥ | Onboard data storage |
| **Encephalon** | 2.0 | 75,000¥ | +2 dice on Intelligence / Logic tests (big-brain decker buy) |
| **Cybercommlink** | 0.2 | 3,000¥ | Built-in commlink (no handset needed) |

### Utility
| Item | Essence | Nuyen | Effect |
|---|---|---|---|
| **Cyberarm** (standard) | 1.0 | 15,000¥ | Replaces limb; socket for arm-mods (hidden compartment, gun-mount post-MVP) |
| **Internal Air Tank** | 0.5 | 6,000¥ | 30 min air supply |
| **Hidden Holster** (Cyberarm mod) | 0.1 | 3,000¥ | Conceals a small weapon in-arm |

## Pipeline

- Cyberware records live in `Data/Gear/Cyberware/<item>.yaml`.
- Each item records: name, essence_cost, nuyen_cost, effects, availability (street index), source (edition + page), description, illustration ref.
- Chargen UI reads from these YAML files; post-chargen street-doc menus read the same list.

## Balance notes

- **Wired Reflexes is king.** Taking Wired Reflexes 2 at chargen plus base essence-heavy gear keeps a street sam at Essence ~3 — functional.
- **Smartlink + Cybereyes + Datajack** = the essential Street Sam / Decker starter stack. Low total Essence cost; big mechanical effect.
- **Awakened can dip** — 0.5 Essence in modest eyes / ears / datajack keeps Magic intact enough for MVP. Anything more is meaningful tradeoff.

## Installation & removal

- **Chargen install** costs nuyen only (assumed downtime / street doc implied). Post-chargen, installation takes in-game time + street-doc fee + recovery.
- **Removal / upgrade** of existing cyberware is possible; doesn't restore Essence (canonical SR). Replacing a cyberlimb with a better one swaps slot but uses the higher of the two Essence costs historically.
- **Used cyberware** (post-MVP): cheaper, available from shady street docs, carries permanent dice-pool penalties ("cultured" vs. used).

## Street doc (MVP)

- One named street doc NPC in the MVP Redmond neighborhood, serves as the post-chargen cyberware vendor and trauma-care provider.
- Offers subset of MVP catalogue; rarer items require contact-raise / rep.

## Open questions

- Exact essence-cost tuning for each item (SR1E numbers vs. playtest calibration).
- Nuyen pricing floor tied to MVP run payout curve.
- Cyberzombies / Deltaware — post-MVP only, flagged in this doc so we remember.
- Cyber-sexual mods (cyber-genitalia, sensation amplifiers, BTL-recording implants) — NSFW pillar suggests including. Deferred to a dedicated pass with NSFW art pipeline available.
- Magic-loss modeling for adepts specifically: their Magic is more fragile than mages' — matches canon but MVP feels harsh. Calibrate.
