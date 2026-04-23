# DESIGN - Magic

## Decision

**DECIDED:** Magic subsystem at MVP covers **Hermetic and Shamanic traditions only**, with **Spellcasting and Spirit Summoning** as core mechanics. Other traditions, Enchanting / alchemy, Initiation / metamagic, and Astral projection depth are **post-MVP**. Full Mage and Physical Adept are MVP-playable archetypes.

## Traditions (MVP)

### Hermetic
- **Approach:** intellectual; magic as a learnable science. Lodges, libraries, formulae.
- **Drain attribute:** **Willpower**.
- **Summoning:** elementals by element type — **Fire, Earth, Air, Water**.
- **Flavor:** classical robes / tattoos / ritual circles; austere.
- **Starting archetype fit:** scholarly mage, cabal member, corp-aligned awakened.

### Shamanic
- **Approach:** relational; magic as communion with totems and spirits of nature.
- **Drain attribute:** **Charisma**.
- **Summoning:** spirits of nature by environment — **City, Forest, River, Mountain, Prairie, Desert, Swamp**.
- **Totem:** required choice. Each totem grants bonuses / imposes restrictions. MVP totems: **Bear** (heal bonuses / penalty vs. urban noise), **Wolf** (combat bonuses / pack loyalty), **Rat** (urban barrens bonuses / greedy), **Cat** (stealth bonuses / aloof), **Raven** (deception bonuses / trickster), **Snake** (illusion bonuses / manipulative). More post-MVP.
- **Flavor:** totem imagery / body-paint / urban-shaman grit; deeply connected to local spirit ecology.
- **Starting archetype fit:** street shaman, Barrens spiritual healer, totem-driven wanderer.

Both traditions have equivalent mechanical power — difference is voice, spirit availability, and ambient roleplay.

## Attributes & rating

- **Magic attribute:** 0 (mundane) to 6 at chargen, 12 absolute. Governs spell force limits, drain resistance ceiling, Astral action.
- **Essence:** cyberware loss drops effective Magic. Effective Magic = `Magic - (6 - Essence)`.
- **Awakened detection:** assensing a character reveals their Awakened status; not a secret in the Matrix or astrally.

## Spellcasting

### Categories (SR core)
- **Combat** — Manabolt, Powerbolt, Fireball, Lightning Bolt, Stunbolt.
- **Detection** — Analyze Truth, Clairvoyance, Detect Life, Mindlink.
- **Health** — Heal, Treat, Antidote, Stabilize, Increase Reflexes, Cure Disease.
- **Illusion** — Invisibility, Trid Phantasm, Silence, Chaotic World, Mask.
- **Manipulation** — Levitate, Armor, Barrier, Magic Fingers, Influence, Control Actions.

MVP content: **~12–15 spells** across categories. Expand post-MVP.

### Cast resolution

1. Mage chooses **target** and **Force** (up to Magic × 2).
2. Roll **Sorcery** (skill) against **TN = target's relevant defense** (Body for direct damage spells, Willpower for mental manipulation, etc.).
3. Successes vs. defender's resist roll determines effect strength.
4. Mage resists **Drain** = Drain code of the spell (varies). Pool: **drain attribute × dice** vs. **TN derived from Force**.
5. **If Force > Magic rating:** Drain is **Physical** instead of Stun. Dangerous.

### Sustained spells
- Some spells persist (Invisibility, Armor, Levitate). Sustaining reduces dice pools by -2 per sustained spell.
- **Sustaining focus** (post-MVP gear) allows offloading this penalty.

### Line-of-sight requirement
- Most Combat / Manipulation spells require LOS.
- Detection / Divination can reach astrally or through relationships.

## Spirit summoning

### Hermetic (elementals)
- Summon in a **prepared lodge** (ritual hermetic space). MVP: lodge in PC's apartment.
- Choose **type** (Fire / Earth / Air / Water) and **Force**.
- **Summoning** test: Sorcery (Conjuring sub-skill for MVP) vs. Force TN. Successes = **services owed**.
- Drain as per spell rules (Willpower, Physical if Force > Magic).
- Spirit provides **services** (one action per service): combat, concealment, search, guard, scout, message, remote manipulation.

### Shamanic (nature spirits)
- Summon in a **domain** — open terrain matching the spirit type (River spirit at water; City spirit on urban streets).
- Otherwise same mechanic as Hermetic.
- Totem influences: some totems favor certain spirit types (e.g. Bear favors Forest/Mountain; Rat favors City).

### Services
- **Combat:** spirit fights alongside the summoner.
- **Concealment:** hides a target from detection (magical and mundane).
- **Guard:** alert summoner if area is breached.
- **Search:** find a named target (uses spirit senses).
- **Remote service:** perform a task at distance (MVP: scout a target location).

### Duration
- Spirit lasts until services consumed or sun rises / location changes (per SR canon). Services are precious.

## Astral projection (MVP: minimal)

- Mages can perceive astrally (assense) as a simple action — reveals auras, magical activity, dual-natured creatures.
- **Full projection** (leaving the body to explore astrally) is **post-MVP**. MVP mages are body-bound except for the assense action.

## Physical Adept

- Adepts spend Magic rating on **powers** instead of spells / summoning.
- **MVP power tree (subset):**
  - **Improved Reflexes** (levels 1–3; costs 0.5 / 1 / 2 Power points) — equivalent to Wired Reflexes but magical.
  - **Killing Hands** — unarmed attacks do weapon-grade damage.
  - **Improved Ability (skill)** — +1 dice per level for a specific skill.
  - **Mystic Armor** — +1 Ballistic / Impact per level.
  - **Pain Resistance** — ignore wound penalty at lower level.
  - **Astral Perception** — assense on demand.
  - **Mystic Shield** — spell defense.
- **Power points:** equal to **Magic rating**. Spend at chargen; respec post-MVP.
- **No spellcasting, no summoning.** Adepts are pure physical-magic.

## Drain

- Spellcasting and summoning both cause Drain.
- Roll **drain attribute** dice (Willpower for Hermetic, Charisma for Shamanic) vs. Drain TN (from Force).
- Successes reduce damage level: Deadly → Serious → Moderate → Light → None.
- Physical vs. Stun: Force ≤ Magic = Stun; Force > Magic = Physical.
- **Drain accumulates in the Stun / Physical track** — same track combat damage uses. Heavy casting in a fight can drop a mage into serious wounds without taking a bullet.

## Magical illicit-economy hooks (cross-ref)

Per-district canon can declare magical illicit-economy hooks. Cross-ref `World/DESIGN - Economy.md`. Examples expected to land when Redmond is ingested:

- **Fire-spirit summoning for arson-for-hire.** Mages contracted for insurance-fraud or corp-hit burns.
- **Blood magic / hexed-reagent market.** Ritual-circle services, illegal reagents, corp "private-use" buyers.
- **BTL-magic chips** — experimental magical effects encoded as BTL content (post-MVP NSFW territory).

## NSFW-magic crossover (hooks)

Given the NSFW pillar, magic has adult terrain too:

- **Influence / Control Actions** spells are non-consent vectors — antagonists may use them on PCs or NPCs. PC use creates reputation / karma consequences per `DESIGN - Reputation.md`.
- **Ritual sex magic** (blood magic / sex magic fusion) as post-MVP content: illegal traditions, specific cults (Bael / Osé / Morrigan-coded), extreme power at extreme cost.
- **Pleasure spirits** as a summonable-service variant (post-MVP, adept-path or specific-tradition).

## Pipeline

- Spell records live in `Data/Systems/Magic/Spells/<name>.yaml`.
- Spirit types: `Data/Systems/Magic/Spirits/<type>.yaml`.
- Adept powers: `Data/Systems/Magic/AdeptPowers/<name>.yaml`.
- Traditions: `Data/Systems/Magic/Traditions/<name>.yaml`.

## Canonical magical communities

Per-district magical community anchors (when they land):

- Expected: **Rat's Nest** in Redmond as Rat-shaman concentration (carried forward from prior Seattle-Sourcebook p.130 ingestion when Redmond is re-ingested).

## MVP content

- **~12–15 spells** across all five categories.
- **Hermetic: 4 elemental spirit types** (Fire, Earth, Air, Water).
- **Shamanic: 6 nature-spirit types** (City, Forest, River, Mountain, Prairie, Desert) + 6 totems (Bear, Wolf, Rat, Cat, Raven, Snake).
- **Adept: ~8 powers** in MVP tree.
- **One lodge location** (PC's apartment; upgradeable post-MVP).

## Open questions

- Sorcery / Conjuring — one skill or two? MVP: consider merging to Sorcery for all magic; Conjuring splits post-MVP.
- Spirit persistence across scenes — services bank or reset on long downtime?
- Adept Power point respec cost (hard rule or narrative-gated)?
- Totem list expansion to all published totems — post-MVP scope.
- Background count / mana-desert zones — simulated or post-MVP?
- NSFW-magic content (sex magic, pleasure spirits) at what MVP depth?
- Foci bonding (post-MVP) — item attunement system.
- Ritual sorcery (long-distance, group-cast) — post-MVP.
