# DESIGN - Combat

## Decision

**DECIDED:** Turn-based tactical combat with **phase-pass initiative**, **square grid**, **full cover + line-of-sight**, **SR1E d6 exploding dice pool** resolution, and **SR1E wound-box damage** (Physical + Stun tracks with dice-pool penalty overflow). Street Samurai archetype is built first; other archetypes plug onto this scaffolding.

## Initiative model — phase-pass

Classic SR1E/2E: everyone acts each **Initiative Pass**; characters with higher Reaction (augmented by Wired Reflexes, Reaction-enhancing magic, adept speed tree) act in **additional passes per round**.

```
Round structure:
  Pass 1: everyone with Initiative ≥ 1 acts (highest goes first)
  Pass 2: everyone with Initiative ≥ 11 acts
  Pass 3: everyone with Initiative ≥ 21 acts
  Pass 4: everyone with Initiative ≥ 31 acts
  ... continues until no one has actions left ...
```

- **Initiative score =** Reaction + d6 exploding (per SR1E), rolled at round start.
- Wired Reflexes 1 = +1 die to Initiative roll + 1 extra Pass.
- Wired Reflexes 2 = +2 dice + 2 extra Passes.
- Effect: a Reaction 8 Wired-2 street sam takes 3+ actions while a Reaction 3 mage takes 1.

**Gameplay feel:** high-reflex characters are dramatically faster, not just "next in line." The speed gradient is the SR identity.

## Grid & movement

- **Square grid.** Simple pathfinding, classic CRPG tactical feel.
- **Tile size:** 1.5m per tile (a human-sized character occupies one tile; Trolls occupy one tile but with collision / reach flags).
- **Movement economy:**
  - **Walk** — up to `Quickness-or-Agility × 2` tiles per pass (free action if below threshold).
  - **Run** — up to `Quickness-or-Agility × 4` tiles; costs action; imposes ranged-attack penalty on attacks against runner (canonical SR).
  - **Dash** — full-action sprint; no attack this pass.
- **Facing** is tracked (for backstabs, AoO, cone-LoS).
- **Terrain cost:** flat tiles = 1 move; rubble/stairs = 2; water/tight = 3.

## Action economy per pass

Each Pass, a character gets:

- **One complex action** (attack, spellcast, complex skill use), OR
- **Two simple actions** (simple attack, reload, quick-move, observe), OR
- One **free action** every pass (speak a short line, drop an item, activate a comms).

## Dice resolution — SR1E d6 exploding

- Roll (relevant attribute + skill) d6s.
- **Any 6 explodes:** roll again, add the new value to that die. Keep exploding on further 6s.
- Count dice **meeting or exceeding the Target Number (TN)**. Those are **successes**.
- **Target Number** is set by difficulty + modifiers (cover, range, visibility, wound penalty, environment).
- **TN 2** = trivial; **TN 4** = standard; **TN 6** = hard; **TN 8+** = dangerous; **TN 12+** = heroic.
- Gear mods, smartlink, specialization: add dice or reduce TN by 1.

### Opposed tests
- Attacker rolls vs. TN; defender rolls dodge / body resist / willpower vs. their own TN. Subtract successes for net.

### Glitches
- **Rule of 1.** If half or more of the dice roll 1, it's a glitch — something goes wrong even on success. Classic SR flavor.

## Damage

### Tracks
- **Physical track:** 10 boxes. Weapons, falling, blood magic.
- **Stun track:** 10 boxes. Tasers, drain, fatigue, some drugs, magical effects.
- **Box-level wound penalties:**
  - Light (1–3 boxes filled): no penalty.
  - Moderate (4–6): **-1 TN** on all tests (equivalently -1 dice pool).
  - Serious (7–9): **-2 TN** on all tests.
  - Deadly (10 boxes): character down; stabilize or die.
- **Stun overflow** → Physical (knock-unconscious and bleeding out).
- **Physical overflow** → death.

### Weapon damage codes (SR1E format)
Each weapon has a damage code like `6M`:
- The **Power** (6) is rolled as a resist TN vs. the target's Body.
- The **Damage Level** (L/M/S/D) maps to the starting box bracket: Light / Moderate / Serious / Deadly.
- Successes after resist escalate / de-escalate the damage level by stage.

Example: a hit with `6M` vs. a target with Body 4, wearing +2 armor:
- Resist pool = 4 (Body) + 2 (armor). Roll vs. TN 6 (weapon Power).
- Each success reduces the damage level by one stage (M → L → nothing).

### Armor
- **Ballistic** (vs. firearms).
- **Impact** (vs. melee, explosives, falls).
- Armor adds to Body for resist *and* sometimes **lowers weapon Power** directly (SR3E-style) — calibration choice for MVP.

## Cover & LOS

- **Cover types:**
  - **Light** (waist-high crate, doorframe): +1 TN to shoot the covered character.
  - **Heavy** (full wall corner, thick table): +2 TN.
  - **Full** (behind a pillar, complete occlusion): no line of sight; no shot.
- Shooter can break cover to shoot (lose cover bonus that pass) or pop-and-drop (half bonus if rules allow).
- **LOS** is enforced on a tile-ray basis; blocked by full cover and thick walls. Smoke / low-visibility imposes additional TN.

## Ranged combat

- **Range bands** (per weapon): Short / Medium / Long / Extreme. Modify TN.
- **Recoil:** single-shot (no penalty), semi-auto (1st round at base, 2nd at +1 TN, etc.), full-auto (one burst — decent base, but aim penalties apply).
- **Smartlink:** -1 TN or +2 dice pool (canonical SR).
- **Called shots:** +4 TN for a specific location (head, eye, limb, weapon hand); higher damage stage or effect (disarm, blind).

## Melee combat

- Adjacent-tile requirement.
- **Reach** matters: Troll reach + polearm can hit one tile away. Shorter reach imposes +1 TN vs. a longer-reach opponent.
- **Attack of Opportunity** when an enemy leaves your melee zone (optional rule; MVP: yes).
- **Backstab:** +2 dice from behind unaware target.

## Magic in combat

See `DESIGN - Magic.md` for spells, summoning, drain. Combat relevant notes:

- Mages declare spell + Force; roll Sorcery; resist Drain.
- **Line-of-sight** required for most spells (some have other targeting rules).
- **Force exceeds Magic rating** = Drain becomes Physical instead of Stun.
- Spirits engage in combat per their own statblock.

## Matrix in combat (interleaved)

- Decker can act on the Matrix during meat combat. The Matrix surface is a parallel scene (see `DESIGN - Matrix.md`).
- Decker's meat body is **vulnerable while jacked in** — guards can dump a hole in the decker while their mind is in the node.
- **Jack-out** is a free action unless interrupted; IC can apply dumpshock (Stun damage or worse) on forced disconnects.

## AI

- **Enemy archetypes (MVP):** ganger (low skill, mobs), go-ganger (motorcycle, hit-and-run), security guard (tactics, cover), street shaman (supports with spells + spirits), decker (Matrix presence).
- **Behavior:** priority-based (self-preservation, objective, target PC). Heavy-cover when injured. Flank when numbers allow. Panic when squad wipes.
- **Morale:** enemies can break and flee if pressure crosses threshold.

## UX

- **Combat HUD:** turn order (with Pass counter), action budget, dice-pool preview on hover, TN preview on target selection, cover indicator on hover.
- **Dice visualization:** animate exploding 6s; show chain. Don't hide the math.
- **Attack chain preview:** before confirming an action, show predicted TN, pool, expected successes, damage range.

## MVP content

- One hand-crafted Redmond combat tileset (fixer bar, back alley, rooftop, gang hangout interior).
- ~6–8 enemy archetypes (ganger, go-ganger, security guard, street shaman, decker, thug, go-gang mage, Lone Star enforcer).
- ~8–12 weapons across Firearms / Armed / Unarmed / Throwing with MVP catalogue depth.
- ~6 armor types (Street jacket, Armor jacket, Secure jacket, Security armor, Heavy armor, Form-fitting bodysuit).

## Open questions

- Final attribute-to-Initiative formula (Reaction pure, or Reaction + Intelligence as SR3E).
- Exact armor model (dice-pool bonus, Power reduction, both).
- Do we show raw exploded-die total, or just successes?
- Glitch UX — visual tell, dialogue effect, or just mechanical?
- Rigger integration (post-MVP) — where do drone combatants live on the turn order?
- Overwatch / held actions — in MVP or post-MVP?
- Environmental hazards (fire, toxic, electrical) — MVP-scope or later?
