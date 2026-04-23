# DESIGN - Factions

## Decision

**DECIDED:** Factions are first-class canonical actors stored under `Data/Lore/Factions/<Name>.yaml`. Each carries structure, turf / presence, leadership, relationships to other factions, game_presence (MVP vs. post-MVP scope), and MVP-visible content hooks. Reputation is tracked per-faction (see `World/DESIGN - Reputation.md`).

## Faction YAML schema (target)

```yaml
name: "Seattle Mafia"
type: "Organized crime"
tier: "AA-equivalent"              # street / gang / organized / AA / AAA

sources:
  - edition: SR1E
    book: "Seattle Sourcebook"
    year: 1990
    page: 128
    image: "Sources/SR1E-Seattle/p128-redmond-outlying.png"

structure:
  leadership:
    - role: "Don"
      npc: "Data/Lore/NPCs/James O'Malley.yaml"
    - role: "Capo"
      npc: "Data/Lore/NPCs/Theodore Alamando.yaml"
  members_estimate: 300

presence:
  - district: "Redmond"
    turf: "Bargain Basement black markets"
    activity_level: "ambient at MVP"
  - district: "Tacoma"
    turf: "dockside protection rackets"
    activity_level: "flavor only at MVP"

relationships:
  allies: []
  rivals:
    - "Yakuza Rings"
  hostile: []
  neutral: ["Lone Star"]

services:
  - "black-market weapons"
  - "protection"
  - "fence / laundering"

game_presence:
  mvp: "ambient (black-market contacts, background events)"
  post_mvp: "direct runs for / against Mafia figures; Del Secondi schism arc"

hooks:
  - "Mafia-tier job offers and retaliations."
  - "Background tension with Del Secondi renegades."
  - "Corruption hooks tying to Redmond city hall."

nsfw_hooks:
  - "Trafficking pipelines (wetwork / rescue runs)."
  - "Extortion of sex-work venues — venue-owner protection arc."

standing_default: 0
thresholds:
  hostile: -60
  unfriendly: -20
  neutral: 0
  friendly: 20
  trusted: 60

revisions: []
```

## Faction categories (anticipated, MVP)

Based on SR1E Seattle canon expected to ingest:

- **Street gangs** (Halloweeners, Redmond Hellhounds, Spikes, Rusted Stilettos, Crimson Crush, Red Hot Nukes, etc. per prior Redmond pages).
- **Specialty crews** (chop-shop / car-jacking / smuggling crews — e.g. Brim Reapers hook from earlier pass, when Redmond p.131 ingests).
- **Organized crime** (Seattle Mafia + Del Secondi renegades, Yakuza Rings, Triads when Seattle-wide material lands).
- **Supremacy groups / extremists** (Humanis Policlub, KKK, The Order).
- **Megacorps** (Aztechnology, Fuchi Industrial Electronics, Renraku, Mitsuhama, Shiawase, and district-specific corps).
- **Local corps / Toxic Castles** (district-specific mid-tier corps like Hollywood Simsense Entertainments, Life-Eze Appliances, Moonshun Vehicles, Carnation Seattle — Redmond-specific from prior pass).
- **Law enforcement** (Lone Star as the privatized police contractor).
- **Magical communities** (Rat-totem shamans at Rat's Nest, hermetic cabals, adept schools — expected when Redmond re-ingests).
- **Media / BBS personas** (Shadowland handles as persona-factions; see `Narrative/DESIGN - Writing.md`).

Authored (non-canonical) factions expected in MVP:

- **Sex-work circles** (independent escort networks, brothel-owner consortium).
- **BTL-producer cartels** (chip-pirate rings, adult-simsense studios).
- **Drug distribution** (street-tier dealer networks under organized-crime umbrellas).

## Faction relationships

- **Allies / rivals / hostile / neutral** lists in each faction file. Symmetric where possible; log asymmetries explicitly (Faction A considers B a rival; B may consider A irrelevant).
- **Interaction effects:** aligning with one can auto-update standing with rivals — sometimes in small ticks, sometimes mandated by run outcomes.

## MVP deliverables

- Faction YAML schema locked.
- Initial faction roster populated as Redmond ingests. No pre-populated stubs before the source pages arrive.
- Rep system driving dialogue / shops / patrols (see `World/DESIGN - Reputation.md`).
- MVP run's Johnson is a **Corporate Mr. Johnson** — his corp is one canonical faction in the `Data/Lore/Factions/` tree. Antagonist faction (the retrieval target's parent) is another.

## Post-MVP

- **Faction vs. faction dynamics** (scripted events firing off relationship graphs).
- **Faction resource flows** (factions "own" shops, contacts, venues — standing affects access across them).
- **Faction war events** (turf skirmishes, rally / counter-rally, gang-on-gang).
- **Corp-tier run chains** arcing across multiple runs of escalating risk against a single AAA.

## Open questions

- Faction-of-factions (Yakuza Rings as umbrella) — one rep axis or per-Ring?
- Standing floor / ceiling — can a faction become permanently hostile (past-recovery)?
- Corp tier vs. street tier of runs — how does standing with one corp affect the world's corp politics?
- Membership vs. patronage — does standing = outsider-favor, or can the PC become an actual Yakuza (member)?
- Sex-work and BTL-producer circles as formal factions — are they one rep each or several?
- Magical communities (Rat totem, Hermetic Cabal) — faction entries, contact clusters, or both?
