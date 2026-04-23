# DESIGN - Redmond

Per-district design sheet. Follows the hybrid template: **sourcebook tabs** (Facts, History, Downtown, Outlying, Government, Economy, Crime, Maps) plus **design additions** (Hooks, MVP Notes, Open Questions).

Canonical data lives in [`Data/Lore/Districts/Redmond.yaml`](../../../Data/Lore/Districts/Redmond.yaml). Sources: **SR1E pp. 127–130**. Policy: **seed — calibrate for play** (see `Setting/DESIGN - Canon.md`).

Named NPCs: [`Data/Lore/NPCs/`](../../../Data/Lore/NPCs/). Factions: [`Data/Lore/Factions/`](../../../Data/Lore/Factions/). Places: [`Data/Lore/Places/`](../../../Data/Lore/Places/).

---

## Facts

| Stat | Value |
|---|---|
| Area | 436 km² |
| Population | **436,000** (canonical) |
| Prose estimate | ~500,000 (300k–700k with transients; p.128) |
| Density | 1,142 / km² |
| Per-capita income | 6,000¥ / year |
| Below poverty level | 70% |
| On Fortune's Active Trackers List | 0% |
| Corporate affiliation | 22% |
| Voting precincts | 15 |
| Hospitals and clinics | 6 |
| Government corruption rate | ~33% (p.128) |
| **LTG prefix** | **11206** (p.129) |
| **Security rating** | **A** (SR worst; p.130) |

Metatype mix (as printed; sums to 106% — retained as canonical):

| Metatype | % |
|---|---|
| Human | 87% |
| Elf | 6% |
| Dwarf | 1% |
| Ork | 10% |
| Troll | 1% |
| Other | 1% |

Education: <12yr 78% · HS 18% · College 3% · Advanced <1%.

**Distribution pattern (p.128):** post-Night-of-Rage metahuman clustering for self-defense. Known concentration: **The Plastic Jungles** (p.130).

## History

Pre-game backdrop (not simulated):

- **2013 — Tritium Services partial meltdown.** Contaminated Beacon Lake and kilometers around it. Origin of Glow City.
- **2028 — Shiawase America replacement plant built** beside Tritium's ruined hulk. Still operational.
- **2029 — Computer Crash.** Economic devastation.
- **2032 — VITAS outbreak.** Population collapse.
- **2039 — Night of Rage.** Drove metahuman clustering.
- **Redmond Hellhounds attack.** Canonical gang incident.
- **Del Secondi Mafia schism.** Executed; renegades persist.
- **2048 — Jeffrey Gasston elected mayor.** Drives recovery project.

## Downtown

No corp-tower downtown. Redmond is post-crash Barrens and decay; commercial remnants cluster at district edges and in the Touristville strip.

## Outlying

Top-level sub-areas:

- **Touristville (aka "Redmond" informal).** Best-developed section of the district, anchored by the Capitol Building and Bellevue proximity. Houses all legitimate tourism. **Seven named neighborhoods** (p.130):
  - **Sophistos** — Squatter
  - **Brats Heaven** — Street
  - **Partys** — Squatter *(spelling uncertain)*
  - **Acondole** — Squatter *(spelling uncertain)*
  - **Klingenpers** — Squatter *(spelling uncertain)*
  - **Woodlanders** — Squatter
  - **Hollywood** — Low (also Red Hot Nukes turf; also Hollywood Simsense facility)
- **Rat's Nest (North Seattle Garbage Center).** Open-air garbage dump; ~1,000 squatters; **canonical Rat-totem shaman concentration** — distinct magical community. See `Systems/DESIGN - Magic.md`.
- **The Plastic Jungles.** 20-greenhouse complex built at the turn of the century on toxic land (harvests contaminated); abandoned post-Crash; now home to much of the district's **metahuman squatter population**.
- **Glow City.** Radioactive zone born of Tritium Services' 2013 meltdown; adjacent to Shiawase America's 2028 replacement plant. Squatter population tripled post-Crash despite cancer and infant-mortality crises.
- **Bargain Basement.** Pre-Crash premium apartments now decayed; illegal power/ventilation hook-ups; street markets and bazaars with Mafia and Yakuza black markets flourishing. Crimson Crush turf.
- **Bellevue-border strip.** Only part of Redmond with functioning civic law; occasional Lone Star patrols.
- **Redmond Barrens.** Umbrella term for the ungoverned majority of the district.

## Government

- **Mayor:** **Jeffrey Gasston** (elected 2048). Mentored by **Governor Schultz**. Champion of the Renton Corner Mall / Redmond Center recovery project.
- **Effective control:** most of the district is **ungoverned**. Only the Bellevue-border strip shows law and order. **Security rating A** (Lone Star worst) across almost all of Redmond (p.130).
- **Corruption:** ~33% of Redmond government tied to Mafia and Yakuza (p.128).
- **Police:** minimum four-man squads; **Aero Citymaster** and **Nissan Patrol-1** riot vans. Regular presence confined to Bellevue-border strip. Per-district override in `Data/Lore/Districts/Redmond.yaml` `police_response`.

## Economy

- **Per-capita income:** 6,000¥/year (≈ 500¥/month) — game-wide anchor.
- **70% below poverty level.**
- **Renton Corner Mall / Redmond Center** is the visible legitimate-economy revival.

### Industrial landscape — "Toxic Castles" + nuclear (p.129, p.130)

Fortified corp compounds with high walls, electric fencing, armed guards, visible pollution:

- **Hollywood Simsense Entertainments** — Hollywood sub-area.
- **Life-Eze Appliances**
- **Moonshun Vehicles**
- **Carnation Seattle**
- **Shiawase America** — nuclear plant in Glow City (AAA anchor).
- **Tritium Services** — defunct; ruined reactor hulk in Glow City.

Plus unnamed petro-chemical refineries, chemical plants, metal recycling centers — fraud pipeline into unscrupulous megacorp supply chains.

### Logistics

Helicopter, tilt-rotor, and **Snoqualmie River barge** shipping — ground shipments attract squatter raids.

### Sub-economies

- **BTL chip trade** — ambient + run-content eligible.
- **Body-parts trade** — **MVP sub-economy**.
- **Inferior industrial products** — ambient fraud.
- **Bargain Basement street markets** — ambient venue; Mafia/Yakuza black markets.

### Named businesses

- **Redmond Phoenix House** — Japanese-American, Union Hill Road, LTG 11206 (63-7516). *[`Data/Lore/Places/Restaurants/`](../../../Data/Lore/Places/Restaurants/)*

## Places of Interest

### Hotels ([`Data/Lore/Places/Hotels/`](../../../Data/Lore/Places/Hotels/))

- **Redmond Center Hotel** (#11.1) — Luxury, Redmond Way, LTG 11206 (34-9001), Salish-American cuisine. Yakuza blackmail rumor on the manager.
- **Lucky Tom Hotel** (#11.4) — Yakuza-adjacent violence; recent wetwork incident.
- **Skoofin Hill Manor & Eat** (#10.5) — Cheap/death-trap, Novelty Hill Road & W. Snoqualmie Valley Road, LTG 11206 (34-0409), owner **Brion Tonugle** (no racial bias).

## Crime

### Gangs (all MVP)

| Gang | Turf / Notes |
|---|---|
| Halloweeners | Fire-themed chaotic street gang. |
| Redmond Hellhounds | District namesake; canonical history. |
| Spikes | Ork-majority go-gang. |
| Rusted Stilettos | Metahuman gang. |
| Crimson Crush | Metahuman gang; **Bargain Basement**. |
| Red Hot Nukes | Metahuman gang; **Hollywood**. |

### Organized crime (ambient in MVP)

- **Seattle Mafia (Redmond branch).** O'Malley / Alamando regime; Del Secondi schism.
- **Yakuza Rings.** 5 Rings; Ill Squires (Don Autigerano) most active. Active in Redmond Center hotels per p.130.

### Supremacy groups (ambient in MVP)

Humanis Policlub, KKK, The Order.

### Illegal economies (MVP)

BTL chip trade; body-parts trade; fraudulent industrial products; Bargain Basement black markets.

## Maps

Target for MVP:
- One hand-crafted Touristville neighborhood (candidate: a specific neighborhood from the seven).
- Two adjacent Barrens streets.
- Canonical anchors: Snoqualmie River, Beacon Lake (Glow City), Union Hill Road, Novelty Hill Road, Capitol Building, Renton Corner Mall / Redmond Center.

## BBS personas

Recurring Shadowland handles (see `Narrative/DESIGN - Writing.md`):

- **Huyen Nick** — recurring (2+ posts); cynical civic-journalism voice. [`Data/Lore/NPCs/Huyen Nick.yaml`](../../../Data/Lore/NPCs/Huyen%20Nick.yaml)
- **Just Another Barrens Squat**, **Marcuson**, **SPD**, **Connie Connostat** — one post each; not yet promoted.
- **Anonymous** — one-off; not persona-tracked.

Media: **Redmond Times Examiner** cited as newspaper source (p.130).

## Hooks

- **Tutorial vector:** Touristville fixer.
- **Six-gang mosaic.** Turf politics as persistent faction substrate.
- **Mafia schism.** O'Malley–Alamando vs. Secondi renegades.
- **Yakuza mall-control plot.** p.130 BBS rumor — Yaks angling for Redmond Center / Renton Corner Mall control. Multi-run arc.
- **Yakuza recruitment pipeline.** Warrior/magician recruits.
- **Supremacy vs. self-defense.** Humanis/KKK/Order vs. metahuman communities.
- **Civic thread.** Gasston's recovery project.
- **Toxic Castle heists.** 5 fortified corp facilities (including Shiawase's nuclear plant).
- **BTL chip trade / body-parts trade / industrial-fraud** runs.
- **Rat's Nest magical community.** Shaman mentor / protection contract / talismonger hook (post-MVP when Magic lands).
- **Plastic Jungles refuge.** Metahuman squatter community; faction conflicts; botany of contaminated harvests.
- **Glow City spectacle.** Nuclear plant + radioactive slum. Post-MVP run territory.
- **Skoofin Hill Manor incident.** Fire/collapse/missing-person seed.
- **Bellevue-border strip.** Fallback zone for under-pressure runners.
- **Poverty-driven runs.**

## MVP notes

Concrete scope (see `Meta/DESIGN - MVP.md`):

- **Geography:** Redmond Barrens only; one hand-crafted Touristville neighborhood (specific name TBD — candidates include Brats Heaven [Street lifestyle] or Hollywood [Low lifestyle + Red Hot Nukes turf + Hollywood Simsense facility = built-in tension]).
- **PC start:** Low-tier apartment, 2,000¥/month.
- **Gangs:** all six present with turf.
- **Organized crime:** Mafia + Yakuza ambient (Yakuza mall-control rumor seeded via BBS).
- **Supremacy groups:** ambient.
- **Corp facilities:** five named (Toxic Castles + Shiawase plant) as ambient backdrop; runs against them post-MVP.
- **Sub-economies:** BTL + body-parts MVP-visible; inferior-products ambient; Bargain Basement markets as traversable venue.
- **Hotels:** three canonical hotels as ambient venues; Skoofin Hill Manor as cheap-crash option.
- **Named NPCs:** Gasston, O'Malley, Alamando, Autigerano, Brion Tonugle peripheral. Huyen Nick as BBS persona.
- **BBS seed corpus:** 12+ posts across pp.127–130.
- **LTG prefix:** 11206.
- **Police:** per-district override; concentrated at Bellevue-border strip.
- **First Johnson:** Touristville fixer with Connection ~3–4.
- **First run:** TBD.

## Open questions

- **MVP Touristville neighborhood.** Which of the seven is the hand-crafted one?
- **First run content.** Retrieval / protection / extraction / sabotage.
- **Body-parts MVP content angle.** Rescue / raid / exposure.
- **Toxic Castle geography.** Neighborhoods for Life-Eze, Moonshun, Carnation Seattle.
- **Gang turf geography at block level.**
- **Metahuman clustering geometry.** Plastic Jungles confirmed; others TBD.
- **Rat-totem community depth.** Post-MVP magical-tutor arc?
- **Neighborhood-name transcription.** Partys / Acondole / Klingenpers spellings need verification.
- **Redmond Center Hotel manager's name.** Transcription unreadable.
- **Full Shadowland-post transcriptions** (pp.127–130).
- **Huyen Nick's on-meat identity.**
- **Carnation Seattle parent company.**
- **Metatype 106% sum.** Normalize or retain?
- **Shiawase America scope.** Do we expand the stub to a full AAA treatment, or wait for more extracts?
