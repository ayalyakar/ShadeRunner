# DESIGN - Combat

Deep-dive pass. Every section below is **DECIDED** unless an **Open questions** subsection qualifies it.

## Core resolution

- **Dice model:** classic SR d6 hit-counting. Roll (Attribute + Skill + modifiers) d6; hits = 5 or 6.
- **Edition anchor:** **custom hybrid distilled from all editions** — SR5's Limits as optional guardrails, SR6's Edge flow, SR4A's karmagen progression, SR1–3's flavor and ordeal structures. No edition wins; each contributes the pieces it does best.
- **Determinism:** every roll is seeded; combat log preserves every die, modifier, threshold, and outcome for inspection.

## Dice visibility

- Default: **hidden** outcome ("11 hits — clean shot through the torso") with tooltip-on-demand showing dice pool, modifiers, target number, and hit breakdown.
- Settings allow "always show dice".
- Full combat log accessible during and after the fight.

## Turn structure

- **Round:** 3 seconds of fiction.
- **Initiative Score:** `Reaction + Intuition + (1d6 per reflex level)` rolled at combat start.
  - Reflex tier adds dice: baseline 1d6, wired reflexes / adept boost stack up to 4d6.
- **Passes:** each round runs passes until every combatant's Initiative Score drops below the pass threshold (10 per SR5/6 convention).
- **Decay:** each pass subtracts 10 from Score.
- **Interrupts:** dodge, parry, counterspell, Matrix defense, edge spends — fire off-pass.
- Edge can **Seize the Initiative** (boost Score mid-round or gain an extra pass).

## Action economy per pass

**Minor-budget pool** (SR6-style):

- Each pass grants **4 Minor actions**.
- **Major action = 2 Minors** (firing a weapon, casting a spell, full melee strike).
- **Minor actions** (1 each): move a short distance, aim, reload, draw, quick dodge, speak, interact, take cover.
- **Free actions** are free (drop item, shout an order, reflex twitch, edge declare).

This lets a pass fire one Major and two Minors, or four Minors, or two Majors (with setup), depending on player choice.

## Damage & wounds

Three stacked layers — all active:

1. **Dual condition tracks** (SR classic): Physical and Stun, one box per Body-derived capacity. Overflow from Physical = dying; overflow from Stun = unconscious. Overflow from Physical into Deadly = PC down.
2. **Hit locations**: every damaging hit resolves to a location (head / torso / left arm / right arm / legs) via attack roll spread or called shot. Each location tracks its own damage and degradation.
3. **Status effects**: bleeding, burning, poisoned, stunned, prone, blinded, deafened, concussed, suppressed, grappled. Each has a tick rate, cleanse action, and escalation path.

### Wound effect stack

A wounded combatant suffers **all three** simultaneously:
- **Dice-pool modifiers** per 3 boxes of damage (classic SR wound modifier).
- **Location impairments**: arm disabled → can't use two-handed weapons; leg crippled → movement halved; head → additional -2 to mental pools.
- **Active statuses** per event: a grenade causing "burning" deals DoT until extinguished.

### Healing pipeline

- **First Aid** (skill) stabilizes wounds and prevents further overflow; stopgap.
- **Biotech** (skill) over downtime treats long-term recovery.
- **Magical healing** (Heal, Treat, Prophylaxis) potent but brings Drain and magical background considerations.
- **Doc Wagon** contracts bill per tier; fast extraction under heavy fire is expensive.
- Baseline recovery is **slow by default** — no auto-heal between fights. A bad run carries wounds into the next day.
- Stun heals faster than Physical; Physical above half requires clinical care to fully resolve.

## Armor

- **SR-style soak + AP.** Armor rating adds to Body for damage resistance; weapon AP (Armor Penetration) reduces effective armor.
- Resistance roll uses `Body + Armor` dice vs. damage value; hits reduce damage one-for-one.
- Armor types have flavors (ballistic, impact) but no layered sub-type complication at this level.
- **Encumbrance and stacking** follow SR hybrid rules: layered armor plates have diminishing returns and mobility costs.

## Cover

- Three tiers: **None / Partial / Full**.
  - None: no modifier.
  - Partial: defender +2 to Defense pool, some lines of fire possible.
  - Full: defender cannot be targeted directly unless attacker maneuvers; no damage unless called shot / AoE / destructible cover breached.
- Cover is **geometric** (line-of-fire check) but graded to three tiers for legibility.
- Cover is **destructible**: sustained fire degrades it (sandbag bursts, wall spalls, glass shatters).

## Ranges

- **Five range bands** per weapon: Close, Short, Medium, Long, Extreme.
- Band modifiers anchored in **ballistic realism** — a Predator pistol is murder at Short, wobbly at Long; a sniper rifle penalized at Close.
- Each weapon has its own band mapping (distances and per-band dice modifier).
- Smartlink corrects selectively (reduces mid-range penalties more than extreme-range).

## Edge system

**Hybrid pool + accrual.**

- Starting Edge pool by attribute (Edge rating 1–7).
- **Situational Edge accrual**: flanking, aiming, surprise, cover advantage, environmental exploitation each generate +1 Edge (cap per combat).
- **Spends** (1 or more Edge each):
  - Re-roll failures.
  - Add hits directly.
  - Seize the Initiative (extra pass or boost Score).
  - Push the Limit (ignore Limit cap on hits).
  - Negate a glitch.
  - Interrupt an enemy action.
- Edge refreshes between combats at a capped rate (not instant).

## Glitches

- **SR-standard:** more 1s than half the dice pool = **glitch**. No hits + glitch = **critical glitch**.
- Glitch consequences scale to context: weapon jam, partial misfire, spell backfire, sound draws attention, reveal.
- Critical glitches are narratively meaningful — a decker critically glitching during a deep dive might reveal their real meat location.
- Edge can **negate** a glitch before resolution (spend Edge).

## Surprise & combat entry

**Two-layer model stacked:**

1. **Awareness-graduated entry** (see `Gameplay/DESIGN - Non-Combat Pillars.md` for the stealth side):
   - Unaware → Suspicious → Alerted → Combat.
   - Combat starts at the current awareness tier; Unaware targets are flat-footed.
2. **Surprise test** on top: `Reaction + Intuition` vs. the ambusher's Stealth (or similar). Losers miss the first pass entirely.

An ambush with good prep can **skip the first pass** for victims and grant **free Edge** to the ambusher.

## Melee

**SR opposed resolution + mini-game overlay.**

- Base math: opposed test — Attacker `(Agility + Melee + Reach)` vs. Defender `(Reaction + Intuition + Melee if parrying)`. Net hits deal damage.
- Overlaid per exchange: **parry / riposte / feint** mini-choices per pass:
  - **Parry:** defender commits Minor action to add defense dice at cost of counter-attack speed.
  - **Riposte:** if defender beats attacker by threshold, free counter-strike.
  - **Feint:** attacker spends Minor to reduce defender's dice next pass.
- Reach, weapon type, and cyber-grafted weapons apply standard SR modifiers.
- Positioning (flank, back, grappled) modifies both defense dice and called-shot viability.

## Spellcasting in combat

- **Full magic pipeline per cast** — no shortcut for combat.
- Spellcasting = Major action (2 Minor actions).
- Full Drain resolution immediately (see `Systems/DESIGN - Magic.md`).
- Sustaining spells drain the mage's dice pool continuously (foci reduce).
- Counterspelling is a dedicated Minor action for any mage holding Counterspell dice in reserve.

## Matrix during meat combat

**Mixed mode** — three behaviors depending on how the decker is jacked:

| Mode | Cost | Timing |
|---|---|---|
| **AR hacks** | 1 Minor action | Resolved inline on meat turn; Electronic Warfare pool; suitable for maglocks, cameras, commlink disruption. |
| **Cold-sim VR** | Normal passes | Resolved on meat time; slower than hot-sim but safer (no dumpshock). |
| **Hot-sim VR** | Separate timeline | Decker's Initiative runs on Matrix timeline (faster); renders as parallel panel during combat; meat body inert. |

Non-decker PC can do AR hacks with Electronic Warfare skill — limited scope but useful.

## Rigging during meat combat

All three modes available per pass; player chooses each turn:

- **Jump-in (full swap):** perspective swaps to drone; PC body vulnerable; drone uses rigger's stats with bonuses.
- **Command from RCC (Minor action):** issue orders to one or more drones; they act on their own Initiative.
- **Autonomous / autosoft:** once deployed, drones follow their autosoft logic without per-pass input.

## Attack options

All first-class, usable with any appropriate weapon:

- **Called shot:** trade dice pool for location or effect (headshot, disarm, leg cripple, knockout).
- **Burst fire / full-auto:** spend extra ammo for bonus hits or recoil penalty; wide or narrow burst.
- **Aim (Minor action):** accumulate +1 die per aim, capped at a per-weapon ceiling.
- **Suppressive fire:** area denial cone; targets inside take Reaction penalties and forced cover / prone reactions; ammo cost high.

## Ammo & gadgets

All modeled with mechanical weight:

- **Full SR ammo taxonomy:** APDS, gel, stick-n-shock, explosive, flechette, tracer, subsonic, capsule rounds. Each interacts differently with armor, stun/physical, status effects.
- **Weapon jams & maintenance:** critical glitches and neglect can jam; clearing is a Minor (or Major for heavy malfunction); maintenance during downtime prevents.
- **Smartlink pipeline:** full mechanical effect (reduced range penalties, free aim integration, ammo counter, target designation) when smartgun-capable weapon + smartlink cyber or goggles are equipped.
- **Tactical items / AoE:** grenades (frag, flashbang, smoke, thermite), glue launchers, EMP, gas; resolve with templated area effects and duration-tracked statuses.

## Enemy AI

Different archetypes use different architectures. The engine supports all of them and picks per NPC:

- **Behavior trees** — for simple archetypes (street gangers, ferals, panicking civilians). Authored, debuggable, predictable.
- **Utility AI** — for mid-tier (corp guards, Lone Star patrols). Scores actions per pass against tactical weights tuned per archetype.
- **GOAP** — for elite archetypes (Knight Errant HTR, runner rivals, awakened threats). Plans multi-turn sequences toward goals.
- **Hybrid BT + utility** — common in practice: BT drives high-level doctrine, utility scores action choice within a node.

Per-archetype AI profiles (weights, plans, priorities) live in data and are tunable.

## Morale

**Full stacked model.**

- **Archetype baseline**: gangers break at first serious hit; Knight Errant HTR fights to the last.
- **Individual bravery stat**: deteriorates with own wounds, friendly deaths, leaderless state.
- **Triggered checks**: outnumbered, seeing a horrific spell, losing their leader, watching a spirit tear a squadmate apart.

Failures produce one of: **surrender**, **flee**, **freeze**, **desperate all-in**.

## Detection & alert propagation

**Full stack.**

- **Per-NPC awareness stages:** Unaware → Suspicious → Alerted → Combat. Stage transitions timed and condition-driven (line of sight, sound, dead body found, etc.).
- **Facility-wide alert state:** every area has an alarm state machine; an alerted guard can raise it; reinforcements and patrol patterns adjust accordingly.
- **Networked propagation:** cameras, sensors, and radio-equipped guards form a graph; alert flows along edges. Cutting power, jamming radio, or killing silently limits propagation.

## Response escalation

**All four layers active**:

1. **Local reinforcements:** guards from adjacent areas / shifts respond first; arrive over 1–5 minutes.
2. **Police response:** Knight Errant / Lone Star patrols (district-dependent) arrive per district response-time table.
3. **Corp HTR teams:** High Threat Response squads dispatched to corp-tier incidents; overwhelming force, mages, HTR rigger with drones. Arrive over 5–20 minutes.
4. **Post-run retaliation:** factions burned by a run don't stop at the fight; counter-runs, contracts on the PC, targeted strikes at the PC's lifestyle / contacts in the days/weeks after.

Escalation timers and intensities scale with target tier and how loud the run was.

### Per-district police overrides

Global police parameters (minimum squad size, standard response vehicles, base response times) can be overridden per district via the `police_response` block in `Data/Lore/Districts/<Name>.yaml`. Reference implementation: Redmond (4-man minimum squads, Aero Citymaster / Nissan Patrol-1 riot vans, ~33% corruption rate) from SR1E p.128.

## Lethality baseline

Calibrated between **tabletop-brutal** and **tactical grind** — call it **High-Medium**:

- An unarmored PC caught in the open against a burst will likely go down.
- Armored, cover-smart, well-positioned PC survives most opening exchanges and can trade for several passes.
- Fights reward preparation, positioning, Edge management, and restraint over rushing in.
- Without Doc Wagon or First Aid, a single bad exchange can keep the PC in recovery for days.

Difficulty sliders (see `Gameplay/DESIGN - Difficulty.md`) can push this either direction.

## Cross-system fire (quick reference)

A single round can see:
- Street samurai firing bursts while sprinting between cover.
- Mage casting a Manabolt and resisting Drain.
- Decker on hot-sim running interference in the Matrix parallel-panel.
- Rigger jumped into a drone laying suppressive fire from above.
- Astrally-projecting shaman engaging a dual-natured threat in the Astral layer.
- All of the above happening within the same 3-second round, resolved on one unified timeline of initiative passes with specialized handlers per subsystem.

## Implementation priorities (for MVP)

For the **MVP street-sam slice** (see `Meta/DESIGN - MVP.md`), only a subset ships:

- Initiative, passes, decay, Edge pool + accrual.
- Minor-budget action economy.
- Dual damage track + one hit-location impairment (head) + bleed status.
- 3-tier cover, 5 range bands for one SMG + one pistol + one melee weapon.
- Armor soak + AP, one ammo type.
- Called shot, burst fire, aim, suppressive fire.
- BT-only enemy AI (gangers), archetype-coded morale.
- 3-stage alert (Unaware / Alerted / Combat — no networked graph yet).
- Local reinforcements only (no police / HTR / retaliation).
- First Aid + slow baseline recovery.

Everything else (GOAP elites, full location impairment, hot-sim parallel panel, HTR teams, full ammo taxonomy) is **post-MVP**.

## Open questions

- Exact per-weapon range band distances / modifiers — needs a calibration sheet.
- Limit caps (SR5-style) — apply as guardrails, as Edge-removable ceilings, or drop entirely?
- Reach numbers for melee (fists → knife → sword → polearm) — need concrete table.
- Aim accumulation cap per weapon — 2, 3, more?
- Hot-sim parallel-panel UX during meat combat — how to render without overwhelming the player.
- Exact Edge-per-combat cap on accrual (2? 3? scaling with Edge attribute?).
- Balance of Doc Wagon pricing vs. run payout curves.
- How much the player can influence cover destruction mechanically (called shot on cover?).
- Friendly fire: handle realistically, abstract away, or player-option?
