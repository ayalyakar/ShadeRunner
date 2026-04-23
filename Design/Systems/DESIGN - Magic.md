# DESIGN - Magic

## Decision

**DECIDED:** Magic is a first-class subsystem with **all SR aspects fully simulated** and **all published traditions / paths playable**:

Aspects:
- **Astral projection & Astral plane exploration**.
- **Spirits & summoning** — full service / binding economy.
- **Enchanting / alchemy / foci** — crafting, reagents, telesma, sustaining items.
- **Initiation & metamagic** — grades, ordeals, masking / centering / shielding / etc.

Paths:
- **Hermetic & Shamanic** — core traditions.
- **All published traditions** — Chaos, Buddhist, Wuxing, Qabbalism, Voudoun, Path of the Wheel, Norse, Christian Theurgy, Druidic, etc.
- **Adepts** (physical magic) — full power tree.
- **Mystic Adepts** — blended, per SR rules.
- **Aspected mages** — restricted schools.
- **Technomancers** — full Resonance path (mechanically adjacent to Matrix; see `Systems/DESIGN - Matrix.md`).

## Core mechanics

- **Magic rating** determines spell force limits, drain resistance, Astral travel.
- **Drain** — every spell / summoning deals Drain; Physical or Stun depending on force vs. Magic rating.
- **Force** — the power of a spell or summon; player-set up to Magic × 2.
- **Thresholds** per spell and per spirit service.
- **Tradition modifiers** — drain attribute, summoning attribute, spirit preferences vary by tradition.
- **Background count** — ambient magical noise per location (blood-soaked alleys boost some traditions, sap others).

## Spellcasting

- **Combat, Detection, Health, Illusion, Manipulation** categories (SR standard).
- Learning new spells requires a teacher, library, or magical lodge; consumes karma and downtime.
- Sustaining a spell reduces dice pools — sustaining foci exist.
- Ritual magic for long-distance effects.

## Spirits

- Each tradition calls specific spirit types (Fire, Man, Beast, Air, Task, Plant, Water, Earth, or tradition-specific equivalents).
- Negotiation-based bargain: services in exchange for payment/sacrifice/respect.
- Spirits have goals; they **don't obey blindly**. Treatment matters long-term.
- Binding is possible but has Karma cost and ethical consequences in the fiction.

## Astral

- Active mage can project; physical body is vulnerable.
- Astral space has its own geography — layered on meat space; auras, wards, dual-natured beings visible.
- Can encounter spirits, astral guardians, other projecting mages.
- Astral combat rules separate from meat combat.
- **Assensing** reveals identity / health / magical state of beings and objects.

## Enchanting / alchemy

- Foci — bond to magician; provide bonuses.
- Preparations — single-use alchemical effects (spells in a bottle).
- Reagents — consumables to push force limits.
- Enchanting requires a lodge and long downtime (see `Character/DESIGN - Downtime.md`).

## Initiation

- Grade-by-grade progression; each grade requires an **ordeal** (fast, meditation, pain, geas, killing, ritual).
- Grades unlock **metamagics**: Masking, Centering, Shielding, Quickening, Anchoring, Channeling, Divining, etc.
- Initiation requires a magical group or solo ordeal at higher cost.
- Magical groups are simulated factions (see `World/DESIGN - Factions.md`).

## Technomancy (cross-link to Matrix)

- Resonance instead of Magic; Submersion instead of Initiation.
- Sprites instead of spirits; complex forms instead of spells.
- Operates on Matrix. No physical cyberdeck needed.
- Shares UI language with Matrix where possible; shares mechanic scaffolding with Magic subsystem.

## Canonical magical communities

Per-district data files can declare **magical-community anchors** — locations that concentrate a specific tradition, totem, or awakened community. These are location-bound hooks for initiation, mentorship, and run content.

Reference implementation: Redmond (`Data/Lore/Districts/Redmond.yaml`) declares:

- **Rat's Nest (North Seattle Garbage Center)** — concentrated **Rat-totem shaman** community (SR1E p.130). Post-MVP hook: shaman mentor access, community-protection contracts, talismonger connections, rat-shaman-specific initiation ordeals and metamagics.

These anchors should be surfaced in the Magic subsystem's tradition / tutor / community-access logic when the subsystem lands.

## Open questions

- Background count fidelity — per tile, per zone, per district?
- Spirit persistence: do summoned spirits have their own memory / relationships over time?
- Initiation ordeal content — how many unique ordeals hand-authored vs. templated?
- Foci bonding and Geasa at scale.
- Astral projection UX with the protag-switch / companion rules.
