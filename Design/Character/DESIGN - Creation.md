# DESIGN - Creation

## Decision

**DECIDED:** Character creation is **karma point-buy across all slices** (metatype, attributes, skills, resources). No priority table. Blank-slate PC. All four playable archetypes selectable; all five SR1E core metatypes available.

## Karma budget

- **Starting karma budget:** TBD numeric, calibrated against MVP run-payout curve so a starting PC feels competent in basic encounters but can't trivialize them. Target: a freshly-created Street Samurai can survive (not dominate) a 3-gangers fight. See `DESIGN - Progression.md` for karma economy.
- **Budget is singular.** The same karma pool funds attributes, skills, resources, spells/programs, cyberware (via nuyen→cyberware conversion). No siloed subpool.
- **Nuyen allocation via karma conversion.** A portion of karma can be traded for starting nuyen at a fixed curve (to buy gear, cyberware, spells, gear foci, magical supplies). Conversion rate TBD.

## Slices

### Metatype
- **Five core SR1E metatypes available:** Human, Elf, Dwarf, Ork, Troll. See `DESIGN - Metatypes.md` for per-metatype mechanics.
- Metatype is **free** in karma cost — no priority-style penalty. Balance is via metatype stat modifiers and social / legal disadvantages embedded in the world (housing, police response, hate-crime events, shop access).
- Metatype choice affects starting attribute ranges, starting essence, racial discrimination beats in dialogue, and some gear slots (e.g. Troll-fit armor).

### Attributes
- **SR3E/4E-style model:** Body, Agility, Reaction, Strength, Charisma, Intelligence, Logic, Willpower + Essence + Magic.
- Metatype modifies min/max ranges per attribute.
- Starting range at chargen: 1 to (metatype racial max, typically 6 for humans).
- **Karma cost curve:** raising an attribute from N to N+1 costs increasing karma (classic SR1E).

### Skills
- **SR1E skill tree, consolidated.** Redundant small-item skills merged (e.g. "Pistols / SMGs / Rifles" collapsed into **Firearms**; specializations preserve flavor). See `DESIGN - Skills.md` (to be written).
- **Skill categories (target list):** Firearms, Heavy Weapons, Armed Combat, Unarmed Combat, Athletics, Stealth, Etiquette, Negotiation, Intimidation, Perception, Streetwise, Electronics (Matrix/cyberdeck), Computer, Biotech (first-aid / street-doc), Driving, Piloting, Magical Theory, Sorcery, Conjuring.
- **Specializations** (+2 dice to specific applications, per SR convention) as a cheap flavor layer.
- **Skill ratings** cap at 6 at chargen, 12 absolute.

### Starting resources (via karma → nuyen)
- Nuyen pool from karma conversion.
- Spend on gear, cyberware, spells known, foci, contacts.
- See `DESIGN - Cyberware.md` for MVP cyberware catalogue.

### Archetype (role, not class)
- **Not a hard gate.** Chargen doesn't lock you into an archetype; archetypes are conventions over the point-buy.
- **MVP-recognized archetypes** (for the run paths to support and for recommended starting builds):
  - **Street Samurai** — high Body / Agility / Reaction / Firearms / Unarmed; wired reflexes; cyberware-heavy.
  - **Physical Adept** — Magic rating with physical adept tree; Unarmed / Athletics-heavy; no spellcasting.
  - **Decker** — cyberdeck + Matrix skills (Electronics / Computer); datajack; cybereyes.
  - **Full Mage** — Magic rating with Hermetic or Shamanic tradition; Sorcery + Conjuring; no cyberware (Essence-sensitive).
- **Build templates.** Chargen offers preset templates per archetype for players who want to skip raw point-buy; each template is legal point-buy output, just pre-assigned.

### Magic tradition (if Awakened)
- **MVP traditions:** Hermetic or Shamanic only. See `Systems/DESIGN - Magic.md`.
- Magic rating purchased as an attribute; cost increases steeply.
- Mages cannot take cyberware above a certain essence threshold without losing Magic rating.

### Background
- **Lifepath-lite.** A short sequence of narrative questions (childhood, first job, what brought you to Redmond, single loss, one contact you already have). Each answer lands **free bonuses** (one contact, a piece of starting gear, a reputation flag) — no karma cost.
- Optional to fill in; skipping grants a baseline package. Skipping also bypasses some late-game reactivity.

## Flow (UI)

```
1. Archetype preview       (preset templates or "custom")
2. Metatype                (stat preview per choice)
3. Attributes              (point-buy; preview derived stats)
4. Skills                  (point-buy; optional specializations)
5. Magic                   (if Magic > 0: pick tradition, initial spells/bonded spirits)
6. Resources               (karma→nuyen; buy gear / cyberware / foci / contacts)
7. Background              (lifepath-lite; free bonuses)
8. Appearance + name       (model / portrait / pronouns / name)
9. Confirm                 (sheet review)
```

## Balance notes

- Essence / Magic trade-off is central. Adepts and mages can take *some* cyber but at steep cost.
- Metatype physical maxima drive identity: Trolls dominate melee but cost on social / housing / gear; Elves get Charisma for social builds but struggle on raw durability.
- Firearms / Armed Combat gate Street Sam power; Sorcery / Conjuring gate Mage power; Computer / Electronics gate Decker power. Skill ceilings matter more than attributes for MVP.

## Open questions

- Exact starting karma budget number.
- Karma-to-nuyen conversion rate.
- Appearance / portrait pipeline (diffusion-generated per chargen choices, or select from a pre-generated palette?).
- Lifepath-lite content — how many branches per node? How much per-archetype specialization?
- Chargen retcon (can the player redo chargen mid-game during a scripted beat)?
- Mid-chargen save / load (is chargen a save point)?
- Can the PC be fully SINless at chargen, or is that a post-MVP state?
- Pronoun / gender handling across metatypes for dialogue reactivity.
