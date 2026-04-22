# DESIGN - Creation

## Decision

**DECIDED:** **Karma point-buy** (SR4A-style) as the chargen method. Single karma budget spent across metatype adjustments, attributes, skills, magic/resonance, gear, qualities. Maximum flexibility; maximum responsibility.

## Why karma point-buy

- Unified currency matches the progression system (see `Character/DESIGN - Progression.md`).
- No A–E priority lock; full customization.
- Matches tabletop feel for experienced SR players.
- Simplifies post-chargen advancement: it's the same currency.

## Allocation categories

At creation the player spends karma on:

1. **Metatype** (fixed cost by type; Troll > Dwarf > Ork/Elf > Human, adjust as per SR5/6 karmagen tables).
2. **Attributes** (Body, Agility, Reaction, Strength, Willpower, Logic, Intuition, Charisma; plus Edge, Magic/Resonance if awakened).
3. **Skills and skill groups** (standard SR skill list; costs escalate per rating).
4. **Magic / Resonance tradition** (adept, mage, shaman, technomancer, etc. — see `Systems/DESIGN - Magic.md`).
5. **Positive qualities** (pay karma for them).
6. **Negative qualities** (refund karma, capped).
7. **Starting nuyen** (conversion rate to karma).
8. **Contacts** (Connection + Loyalty purchased per contact — see `Social/DESIGN - Contacts.md`).
9. **Lifestyle** (starting tier, months prepaid).

## Tooling

- Character creator is data-driven: every attribute/skill/quality is JSON-editable.
- Preview sheet shows derived stats (Initiative, dice pools, Essence) live.
- Warnings for illegal builds (over budget, missing required skills for magic, etc.).
- Save/load partial chargens; re-open to refine.

## Lifepath layer (optional)

As a *presentation* layer on top of the karma build:

- Player can answer lifepath questions (origin district, trigger event, first job, formative loss).
- Answers suggest starting qualities / contacts / skills.
- Player can accept, adjust, or ignore suggestions.
- Produces a starting **backstory hook** that can drive early narrative.

Lifepath is flavor and seed, not a mechanical replacement for point-buy.

## Starting karma budget

- Default ~800 karma (calibrated to SR5/6 karmagen "Prime Runner"), tunable by difficulty.
- Higher difficulty reduces budget; lower increases.

## Open questions

- Exact costs across hybrid editions — needs a dedicated calibration pass.
- Should chargen enforce archetype *focus* to avoid diluted builds, or trust the player?
- Contact budget: separate pool or shared with karma?
- How to present chargen without overwhelming new players (optional templates / presets).
