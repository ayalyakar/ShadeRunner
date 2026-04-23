# DESIGN - Combat

## Decision

**DECIDED:** **Turn-based tactical**, **phase / pass-based** (SR tabletop style). Free-move (grid-less). Dice math is hybrid-calibrated across editions and is **hidden by default with tooltip-on-demand** (see "Dice visibility" below).

## Initiative & turn structure

- **Initiative Score** = Reaction + Intuition + modifiers (wired reflexes, adept boost, drugs, cyber). Edition-hybrid formula; ~SR5/6 style.
- Round = 3 seconds.
- Each round has multiple **initiative passes**; combatants with higher Initiative Score get more passes.
- Between passes, Initiative decays; combatants act until their Score drops below the threshold.
- Interrupt / reaction actions (dodge, parry, counterspell, Matrix defense) fire off-pass.

## Action economy (per pass)

- **Major action** (shoot, full-power strike, full cast).
- **Minor actions** (move, aim, reload, quick dodge) — several per pass depending on rules.
- **Free actions** (speak, drop item, call spirit assistance).
- Edge spend allowed at any time (re-roll, push limits, seize initiative, extra pass).

## Positioning & movement

- **Grid-less** movement with measured distances.
- Cover is geometric (line-of-fire check), graded full / partial / none.
- Elevation matters.
- Ranges: Close / Short / Medium / Long / Extreme with per-weapon modifier curves.

## Dice pools

- Classic SR d6 pools: attribute + skill + modifiers.
- Hits = 5s and 6s.
- Thresholds, margins, glitches, critical glitches all simulated.
- Resolved on a custom fast path (`Technology/DESIGN - Engine.md`) for large encounters.

## Dice visibility

- Default: **hidden** — a clean UI shows outcome.
- Tooltip-on-demand: hover an action to see dice pool, modifiers, target number, resolved hits.
- Combat log retains the math history for post-match inspection.
- Can be flipped in settings to "always show".

## Damage & wounds

- Physical and Stun condition tracks (classic SR).
- Overflow from Physical into Deadly → unconscious / dying state.
- Armor reduces or converts damage per hybrid rules.
- Wound modifiers reduce dice pools as wounds accumulate.

## Cross-subsystem fire

A combat round can mix all systems at once:
- Meat combat (guns, melee, cyberware).
- Astral combat (for dual-natured / active mage).
- Matrix cross-attacks (decker dropping IC on an attacker's commlink).
- Rigger jump-in with a drone supporting the encounter.
- Spirit summons and spells as their own actions with drain.

## AI

- Enemy archetypes with doctrines (gang brawler, corp security, HTR, Knight Errant).
- Behavior trees or utility AI; plays tactical cover, focus-fire, retreats when appropriate.
- Morale: enemies can rout, surrender, flee.

## Open questions

- Exact hybrid dice-pool formula sheet (needs calibration doc).
- Reach mechanics and weapon-length interplay in melee.
- Surprise / ambush rules.
- Balance tension between tabletop fidelity and videogame legibility in a dice-heavy system.
