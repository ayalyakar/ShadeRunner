# DESIGN - Redmond

Per-district design sheet. Follows the hybrid template: **sourcebook tabs** (Facts, History, Downtown, Outlying, Government, Economy, Crime, Maps) plus **design additions** (Hooks, MVP Notes, Open Questions).

Canonical data lives in [`Data/Lore/Districts/Redmond.yaml`](../../../Data/Lore/Districts/Redmond.yaml). Sources: **SR1E pp. 127–129**. Policy: **seed — calibrate for play** (see `Setting/DESIGN - Canon.md`).

Named NPCs: [`Data/Lore/NPCs/`](../../../Data/Lore/NPCs/). Factions: [`Data/Lore/Factions/`](../../../Data/Lore/Factions/).

---

## Facts

Authoritative figures from the transcribed fact sheet (p.127):

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

**Distribution pattern (p.128):** since the Night of Rage (2039), metahumans **cluster in specific neighborhoods** for self-defense rather than distributing evenly. Procgen honors this clustering (see `World/DESIGN - Procgen.md`).

## History

Pre-game backdrop (referenced in dialogue, BBS, news archives — not simulated):

- **2029 — Computer Crash.** Economic devastation; district never fully recovered.
- **2032 — VITAS outbreak.** Population collapse; social fabric broken.
- **2039 — Night of Rage.** Drove metahuman clustering / self-defense patterns.
- **Redmond Hellhounds attack.** Canonical gang incident that shaped the Barrens.
- **Del Secondi Mafia schism.** Del Secondi and supporters declared independence from Seattle Mafia; Del Secondi executed; renegade faction continues to challenge for control.
- **2048 — Jeffrey Gasston elected mayor.** Drives the Renton Corner Mall recovery project.

In-game canonical events (simulated at their canonical dates if the PC lives long enough):

- *(to be filled as the district is written through the decades)*

See `Setting/DESIGN - Canon.md` for pre-game-backdrop vs. in-game-simulated policy.

## Downtown

Redmond has no real "downtown" in the corp-tower sense; the district is **post-crash Barrens and decay**. Commercial remnants concentrate toward the district edges.

Planned hand-built ground for MVP: **Touristville strip** (see MVP Notes below).

## Outlying

- **Redmond Barrens.** Lawless core of the district. MVP starter ground.
- **Touristville.** Shadow-tourism strip: bars, strip clubs, illicit commerce, Johnson meets. The MVP's single hand-crafted sub-zone.
- **Glow City.** Radioactive ruin. Backdrop only in MVP — visible from the skyline but not enterable.
- **Bargain Basement.** Crimson Crush turf (p.128).
- **Hollywood.** Red Hot Nukes turf (p.128); also hosts Hollywood Simsense Entertainments' Redmond facility — built-in gang-vs-corp tension.
- **Bellevue-border strip.** The only part of Redmond with functioning civic law (p.129); occasional Lone Star patrols.

## Government

- **Mayor:** **Jeffrey Gasston** (elected 2048). Young, politically green at first, mentored by **Governor Schultz**; gaining savvy across terms. Championing the Renton Corner Mall as economic-revival flagship.
- **Effective control (p.129):** Most of the district is **not meaningfully governed**. Only the Bellevue-border strip shows respect for law and order. Civic services, code enforcement, and tax collection are effectively suspended across the majority of Redmond.
- **Corruption:** ~33% of Redmond government tied to the Mafia and Yakuza (p.128). Bribery channels plentiful; reliability of official channels reduced.
- **Legal jurisdiction:** Seattle Metroplex under UCAS; Barrens functionally lawless.
- **Police:** minimum four-man squads per patrol; vehicles are **Aero Citymaster** and **Nissan Patrol-1** riot vans. Regular patrol presence confined to the Bellevue-border strip; deep Barrens sees only occasional patrols. See `Data/Lore/Districts/Redmond.yaml` `police_response` — canonical **per-district override** of the global escalation model (`Systems/DESIGN - Combat.md`).

## Economy

- **Per-capita income:** 6,000¥/year (≈ 500¥/month) — game-wide calibration anchor (see `World/DESIGN - Economy.md`).
- **70% below poverty level.** Squatter and Street lifestyles dominate.
- **22% corporate affiliation** concentrated at district edges.
- **Renton Corner Mall** is the visible legitimate-economy revival project.

### Industrial landscape — "Toxic Castles" (p.129)

Only a handful of major corps operate in Redmond. Facilities are fortified compounds (high walls, electric fencing, armed guards) continuously spewing poisons into the air — nicknamed **"Toxic Castles"**. Named corps (all with stubs under `Data/Lore/Factions/`):

- **Hollywood Simsense Entertainments** — simsense/entertainment; Hollywood sub-area.
- **Life-Eze Appliances** — consumer appliances.
- **Moonshun Vehicles** — vehicles / light automotive.
- **Carnation Seattle** — product domain TBD; regional subsidiary.

Unnamed smaller operators: petro-chemical refineries, chemical plants, metal recycling centers — these move **inferior products to unscrupulous megacorps** (p.129) who resell elsewhere.

### Logistics

Ground shipments attract desperate squatters; factories rely on **helicopter**, **tilt-rotor aircraft**, and **Snoqualmie River barge** shipping instead. Both air and river logistics are run-content vectors (intercept, escort, sabotage).

### Sub-economies (ambient or MVP-eligible)

- **BTL chip trade** — most "successful" Redmond businesses actually sell BTL. Canonical per p.129. MVP-ambient with run-content potential.
- **Body-parts trade** — thugs kidnap squatters, back-alley butcher shops, organs sold to wealthy SINners. **MVP sub-economy** — high-heat, morally grey run content.
- **Inferior industrial products** — fraud pipeline into megacorp supply chains; ambient.

### Named businesses

- **Redmond Phoenix House** — Japanese-American restaurant on **Union Hill Road**, LTG# 11206 (63-7516). First canonical Redmond business address; plausible neutral meet spot.

## Crime

### Gangs (all MVP)

| Gang | Notes |
|---|---|
| Halloweeners | Fire-themed chaotic street gang. |
| Redmond Hellhounds | District's namesake; canonical history. |
| Spikes | Ork-majority go-gang. |
| Rusted Stilettos | Metahuman gang (p.128). |
| Crimson Crush | Metahuman gang; Bargain Basement turf. |
| Red Hot Nukes | Metahuman gang; Hollywood turf. |

### Organized crime (ambient in MVP)

- **Seattle Mafia (Redmond branch).** Nominal Don: **James O'Malley**; Capo: **Theodore Alamando**. Internal turmoil since the executed **Del Secondi** schism.
- **Yakuza Rings.** 5 known Rings in Redmond used as recruitment pool. **Ill Squires** (Don **Autigerano**) most active.

### Supremacy groups (ambient in MVP)

- **Humanis Policlub**, **KKK**, **The Order** all active. Spread human-supremacy rhetoric. Metahuman counter-organizing for self-defense is a visible response.

### Illegal economies (MVP)

- **BTL chip trade** — see Economy.
- **Body-parts trade** — see Economy. MVP sub-economy; high-heat; runs include victim extractions, butcher-shop raids, buyer-exposure jobs.
- **Fraudulent industrial products** — ambient.

### Law enforcement

Law response is slow and under-resourced for the Barrens; see Government section above for the canonical patrol data.

## Maps

To be authored (hero streets + procgen fill). Target for MVP:
- One hand-crafted Touristville block (fixer bar, cheap eats, alley, strip-club entrance, fleabag motel).
- Two adjacent Barrens streets (the PC's apartment, a corner store, a gang hang).
- Canonical geographic anchors: **Snoqualmie River** (also a logistics artery), **flat terrain** with hills in the southern end, **Renton Corner Mall** and **Union Hill Road** as visible landmarks.

## BBS personas

Recurring Shadowland handles are tracked as persistent NPC personas (see `Narrative/DESIGN - Writing.md`).

- **Huyen Nick** — recurring (2+ posts from p.129); cynical civic-journalism voice. Profile at [`Data/Lore/NPCs/Huyen Nick.yaml`](../../../Data/Lore/NPCs/Huyen%20Nick.yaml).
- **Just Another Barrens Squat** — one post so far; not yet promoted.
- **Marcuson** — one post so far (p.128); not yet promoted.
- **Anonymous** — one-off; not persona-tracked.

## Hooks (design additions)

- **Tutorial vector.** Touristville fixer calls the PC cold. Low-stakes intro job leads into the district's broader web.
- **Multi-gang mosaic.** Six gangs share the Barrens; turf politics is the persistent faction substrate.
- **Mafia schism.** The O'Malley–Alamando regime vs. Del Secondi's surviving renegades is a live conflict the player can exploit.
- **Yakuza recruitment pipeline.** Promising street talent (warrior or magician) can be drawn into the Ill Squires.
- **Supremacy vs. self-defense.** Humanis/KKK/Order vs. organized metahuman communities.
- **Civic thread.** Mayor Gasston's recovery project is a vector for both corruption-exposure and corporate-adversary runs.
- **Toxic Castle heists.** The four named corp facilities are viable corp-tier targets with distinct fortifications and logistics (air/river).
- **BTL chip trade.** Run-content opportunities for supply-chain, demand-side, or police-front-operation angles.
- **Body-parts trade.** Victim rescues, butcher-shop raids, buyer-exposure jobs — all morally loaded.
- **Bellevue-border strip.** The district's "lawful" border is a natural fall-back zone for under-pressure runners and a natural trap vector for patrolled arrests.
- **Poverty-driven runs.** Exploitation, debt, body-shopping, missing persons.
- **Glow City spectacle.** Visible skyline; occasional runs to the edge; full interior deferred to post-MVP.

## MVP notes

Concrete scope for the vertical slice (see `Meta/DESIGN - MVP.md`):

- **Geography:** Redmond Barrens only; Touristville strip as the one hand-built sub-zone.
- **PC start:** Low-tier apartment, 2,000¥/month rent due pressure.
- **Gangs:** all six present with turf.
- **Organized crime:** Seattle Mafia and Yakuza Rings ambient.
- **Supremacy groups:** ambient presence.
- **Corp facilities:** four named Toxic Castles as ambient backdrop / visible landmarks; runs against them deferred post-MVP.
- **Sub-economies:** BTL chip trade + body-parts trade as MVP-visible economies (BBS chatter, street gossip, possible runs); inferior-products fraud ambient.
- **Named NPCs:** Gasston, O'Malley, Alamando, Autigerano statted but peripheral to the first run. Huyen Nick as a BBS persona pumping posts into the seed corpus.
- **First Johnson:** Touristville fixer with Connection ~3–4.
- **First run:** type **TBD**.
- **NPC procgen:** district metatype percentages + neighborhood-level clustering + LTG prefix 11206 for procgen commlink / business numbers.
- **Police response:** canonical per-district override (4-man squads, Aero Citymaster / Nissan Patrol-1, Bellevue-border-strip concentration).

## Open questions

- **First run content.** Retrieval / protection / extraction / sabotage — deferred decision.
- **Body-parts MVP content.** Which angle (victim rescue / butcher raid / buyer exposure) ships first?
- **Toxic Castle geography.** Which neighborhoods host Life-Eze, Moonshun, Carnation Seattle? Hollywood locked for Hollywood Simsense.
- **Exact Touristville layout.** Street-level plan for the hand-crafted block.
- **Gang turf geography.** Specific blocks / streets owned by each of the six gangs.
- **Metahuman clustering geometry.** Which Redmond neighborhoods skew metahuman-heavy.
- **Shadowland post transcription** (p.127 / p.128 / p.129 posts).
- **Huyen Nick's on-meat identity.** Purely BBS, or a physical NPC with a persona?
- **Carnation Seattle parent company.** "Seattle" suffix implies a larger Carnation — is this the dairy/food Carnation, or a reinterpretation?
- **Metatype percentage 106% sum.** Keep canonical or renormalize for procgen? Currently retained as-is.
