# DESIGN - Metatypes

## Decision

**DECIDED:** All five SR1E core metatypes are **playable at chargen in MVP**: Human, Elf, Dwarf, Ork, Troll. Stat modifiers follow SR1E with later-edition (SR3E/4E) attribute model (Agility split from Quickness). Metatype adds mechanical modifiers *and* social / world-state reactivity (housing, law, hate-crime events, shop access, dialogue barks).

## Attribute baseline (SR3E/4E-style 9-attribute model)

Base attribute minimum / maximum for chargen. Metatype modifiers apply on top.

| Attribute | Human min | Human max |
|---|---|---|
| Body | 1 | 6 |
| Agility | 1 | 6 |
| Reaction | 1 | 6 |
| Strength | 1 | 6 |
| Charisma | 1 | 6 |
| Intelligence | 1 | 6 |
| Logic | 1 | 6 |
| Willpower | 1 | 6 |
| Essence | 6 | 6 (starting; cyberware degrades) |
| Magic | 0 | 6 (only if Awakened, via attribute purchase) |

## Metatype modifiers (MVP)

Modifiers applied to the baseline min/max. Humans are the baseline. Numbers are starting-chargen ceilings; racial maxima can be raised post-chargen via initiation / metamagic / magic ritual at large karma cost.

### Human
- **Role:** the jack-of-all-trades; no stat penalties.
- **Mins/maxes:** all 1 / 6.
- **Social:** default legal status; no housing / shop discrimination.
- **Notable:** highest Essence headroom without racial loss; best cyberware canvas.

### Elf
- **Mods:** Quickness-equivalent split: **+1 Agility max (7) · +1 Charisma max (8)**. Body/Strength unchanged.
- **Social:** beautiful / exotic register in dialogue; some metahuman-allied factions react positively, some Humanis react negatively.
- **Notable:** top ceiling on social / face builds; strong dexterity ceiling for adepts / stealth.

### Dwarf
- **Mods:** **-1 Reaction max (5) · +1 Body max (7) · +1 Willpower max (7) · +1 Strength max (7)**. Short reach (melee disadvantage TBD); immune to some poisons.
- **Social:** mostly accepted; lawful societies more tolerant than Elves or Trolls.
- **Notable:** tankiest human-adjacent frame. Good Willpower ceiling = magic resist.

### Ork
- **Mods:** **+2 Body max (8) · +1 Strength max (7) · -1 Charisma max (5) · -1 Logic max (5)**.
- **Social:** heavy discrimination in Downtown / corp areas; most accepted in Redmond Barrens. Humanis active threat.
- **Notable:** durability + muscle floor; lives short (aging accelerated — flag in `DESIGN - Aging.md` when written).

### Troll
- **Mods:** **+4 Body max (10) · +4 Strength max (10) · -1 Quickness-equivalent — clarify under split model: -1 Agility max (5), -1 Reaction max (5) · -2 Charisma max (4) · -1 Intelligence max (5) · -1 Logic max (5)**. Dermal armor +1 (SR1E canonical); horns; long reach.
- **Social:** extreme discrimination. Most venues won't let Trolls inside. Housing options severely limited. Troll-sized gear costs more.
- **Notable:** extreme physical ceiling; extreme social / cognitive floors. Most punishing metatype to roleplay; highest damage ceiling.

## Magic-metatype interaction

- All five metatypes can be Awakened (mage, shaman, or adept). No magic/metatype block.
- **Shaman totem availability** can be metatype-flavored in narrative — e.g. Rat-totem shamans are stereotypically Ork or human Barrens residents, Wolf-totem is metahuman-friendly, Bear-totem is Dwarf-associated. No mechanical lock; flavor only.

## Social / world reactivity

World systems respond to metatype beyond stats. MVP scope:

- **Housing.** Landlord reactions vary by metatype; some Bargain-Basement landlords won't rent to Orks or Trolls.
- **Shops / venues.** Some Downtown Touristville venues refuse Trolls / Orks.
- **Police / Lone Star.** Stop-and-frisk probability scales with metatype at Security rating A districts.
- **Dialogue barks.** Random NPCs deliver metatype-appropriate one-liners (positive, neutral, hostile).
- **Faction relations.** Humanis / KKK / The Order react sharply negatively to metahumans. Metahuman self-defense groups and some gangs react positively.
- **Hate-crime events.** Ambient simulation can roll hate-crime incidents where metahumans are targets; these are player-witnessable and sometimes player-interruptible.

## Appearance / art pipeline note

- Each metatype has a diffusion-prompt template (size, proportions, features, tusks/horns/ears) fed by the chargen portrait pipeline. See `Technology/DESIGN - AI Tooling.md`.
- Static portraits for MVP; 3D models in Godot rigged per-metatype.

## Open questions

- Exact numeric mods per split-Agility model — SR1E only used Quickness; SR3E/4E split differently. Lock a final table.
- Troll-size gear economy — cost multiplier, availability reduction, or both.
- Ork aging — mechanical (reduced starting karma / accelerated in-game aging) or narrative?
- Dwarf reach penalty in melee — flat dice-pool mod or positional?
- Metahuman discrimination event frequency — calibrate against frustration budget.
- Non-core metatypes (Shapeshifters, Drakes, Centaurs) — post-MVP consideration.
