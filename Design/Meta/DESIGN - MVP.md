# DESIGN - MVP

## Decision

**DECIDED:** The MVP is one district, one archetype, one run type:

- **District:** Redmond Barrens (Seattle). Hand-built sub-zone: **Touristville strip**. See `Design/Setting/Districts/DESIGN - Redmond.md` and `Data/Lore/Districts/Redmond.yaml` for canonical data.
- **Archetype:** Street samurai (physical combat; also covers physical adept with minor tweaks).
- **Run type:** A single, specific run structure (framed below).

The MVP is **shippable to self**: complete end-to-end, no placeholders in the critical path.

## Concrete Redmond Barrens scope

- **Geography:** Redmond Barrens only; Touristville strip as the one hand-crafted sub-zone (fixer bar, cheap eats, alley, strip-club entrance, fleabag motel). Two adjacent Barrens streets: the PC's apartment, a corner store, a gang hang.
- **PC start:** Low-tier apartment at 2,000¥/month. Monthly rent pressure is the baseline economic stake.
- **Factions present (gangs, MVP turf):**
  - **Halloweeners** — fire-themed chaotic street gang.
  - **Redmond Hellhounds** — the district's namesake gang.
  - **Spikes** — ork-majority go-gang.
  - **Rusted Stilettos** — metahuman gang (p.128).
  - **Crimson Crush** — metahuman gang; Bargain Basement turf.
  - **Red Hot Nukes** — metahuman gang; Hollywood turf.
- **Organized crime (ambient in MVP):**
  - **Seattle Mafia (Redmond branch)** — James O'Malley, Theodore Alamando; Del Secondi schism as live background.
  - **Yakuza Rings** — 5 Rings; Ill Squires (Don Autigerano) most active; recruitment pipeline as BBS / dialogue flavor.
- **Supremacy groups (ambient in MVP):**
  - **Humanis Policlub**, **KKK**, **The Order** — rally events, hate-crime incidents, BBS chatter; metahuman-defense counter-presence surfaced in neighborhood NPC clustering.
- **Canonical NPCs with game presence:** Mayor **Jeffrey Gasston**, **James O'Malley**, **Theodore Alamando**, **Don Autigerano**. All statted but peripheral to the first run. Governor Schultz, Del Secondi as flavor only.
- **Police response (canonical per-district override):** minimum 4-man squads; riot-van vehicles (Aero Citymaster, Nissan Patrol-1); ~33% of Redmond government corruption-linked to the syndicates.
- **First Johnson:** a **Touristville fixer** (Connection ~3–4) who calls the PC cold. Meet happens in a Touristville bar.
- **First run:** content **TBD** (deferred; retrieval / protection / extraction / sabotage).
- **NPC populations:** procgen driven by the district's canonical demographics (87% human, 10% ork, 6% elf, 1% dwarf, 1% troll, 1% other; 70% below poverty; 78% <12-years education) **plus neighborhood-level metahuman clustering** (p.128 post-Night-of-Rage self-defense pattern).

## Why these choices

- **Redmond Barrens:** classic SR starting territory, gang-heavy, lawless, gives meaningful diversity of encounters without corp-tier security.
- **Street samurai:** validates combat (the hardest system to get right) first. Matrix, magic, rigging stubbed for later.
- **One run type:** forces a complete vertical slice instead of broad shallow coverage.

## MVP scope — what's in

- Chargen: point-buy karma, Core 5 metatypes, street-sam-viable skills / gear only.
- A single Redmond Barrens neighborhood hand-built, walkable in first-person and isometric.
- Combat: phase-pass turn-based, free-move, dice-pool engine, one weapon type (e.g. SMG) and one melee type.
- One Johnson, one fixer, one contact archetype: meet the Johnson, take the job.
- Run structure: Meet → Legwork (light) → Execution → Payout.
- Lifestyle: one Squatter / Low tier with monthly rent due.
- Day / night clock.
- Save anywhere (no ironman yet).
- Basic heat tracking.
- Basic reputation tracking (street cred increment on success).
- Minimal UI: character sheet + combat HUD + commlink notifications.

## MVP scope — what's explicitly out

- Magic, Matrix, rigging subsystems (all stubbed or skill-gated out).
- Other metatypes beyond Human + Ork (optional: add Elf).
- Multi-district.
- Era transitions (MVP stays in a fixed year).
- NPC schedules at scale (MVP uses simple routines for ~20 named NPCs).
- Romance / contacts beyond the minimum two.
- Procgen side runs.
- 2D painted cutscenes (placeholder panels only).
- Full voice acting (TTS placeholder).
- Investigation case-board (one lightweight scripted run).

## Acceptance criteria

1. Start new game → chargen → wake up in Redmond Barrens.
2. Receive a fixer call → attend Johnson meet → accept a run.
3. Do minimal legwork (one dialogue scene, one Perception check).
4. Execute the run end-to-end (stealth or combat path, both viable).
5. Collect payout, gain karma and street cred.
6. Return to safehouse, time advances, rent bill approaches.
7. Save, quit, reload — all state preserved.

If any step breaks, the MVP is not done.

## Post-MVP priorities (order TBD)

1. **Matrix subsystem v1** — integrate decker contacts and security-bypass puzzles.
2. **Magic subsystem v1** — add awakened archetype (adept first, mage second).
3. **Rigging subsystem v1** — basic drone jump-in.
4. **Second district** — open up another Seattle neighborhood.
5. **NPC simulation v2** — scale named NPC count and schedule fidelity.
6. **Era transitions** — ship 2050 → 2064 including Crash 2.0 event.

Which of 1–3 comes first is an **open question** (see `Design/DESIGN - Production.md`).

## Open questions

- Exact acceptance test for "feels like Shadowrun" — define metrics or trust playtest?
- How much polish before declaring MVP done (perfectionism risk).
- Should the MVP have any single save preserved for future content as a legacy save format?
- Is there any value in a pre-MVP "tech demo" (combat-only prototype) to validate Godot + custom modules earlier?
