# DESIGN - Redmond

Per-district design sheet. Follows the hybrid template: **sourcebook tabs** (Facts, History, Downtown, Outlying, Government, Economy, Crime, Maps) plus **design additions** (Hooks, MVP Notes, Open Questions).

Canonical data lives in [`Data/Lore/Districts/Redmond.yaml`](../../../Data/Lore/Districts/Redmond.yaml). Sources: **SR1E pp. 127–128**. Policy: **seed — calibrate for play** (see `Setting/DESIGN - Canon.md`).

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
- **Hollywood.** Red Hot Nukes turf (p.128).

## Government

- **Mayor:** **Jeffrey Gasston** (elected 2048). Young, politically green at first, mentored by **Governor Schultz**; gaining savvy across terms. Championing the Renton Corner Mall as economic-revival flagship.
- **Corruption:** ~33% of Redmond government tied to the Mafia and Yakuza (p.128). Bribery channels plentiful; reliability of official channels reduced.
- **Legal jurisdiction:** Seattle Metroplex under UCAS; Barrens functionally lawless.
- **Police:** minimum four-man squads per patrol; vehicles are **Aero Citymaster** and **Nissan Patrol-1** riot vans. See `Data/Lore/Districts/Redmond.yaml` `police_response` — this is a canonical **per-district override** of the global escalation model (`Systems/DESIGN - Combat.md`).

## Economy

- **Per-capita income:** 6,000¥/year (≈ 500¥/month) — game-wide calibration anchor (see `World/DESIGN - Economy.md`).
- **70% below poverty level.** Squatter and Street lifestyles dominate.
- **22% corporate affiliation** concentrated at district edges.
- **Few companies operate factories in Redmond** (p.128); each is massively fortified and hires orks as guards.
- **Renton Corner Mall** is the visible economic revival project.

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
- **Yakuza Rings.** 5 known Rings in Redmond used as recruitment pool. **Ill Squires** (Don **Autigerano**) most active. Recruit warriors and magicians; promising warriors receive cyberware, promising magicians get library / magical cache access.

### Supremacy groups (ambient in MVP)

- **Humanis Policlub**, **KKK**, **The Order** all active. Spread human-supremacy rhetoric. Metahuman counter-organizing for self-defense is a visible response.

### Law enforcement

Law response is slow and under-resourced for the Barrens; see Government section above for the canonical patrol data.

## Maps

To be authored (hero streets + procgen fill). Target for MVP:
- One hand-crafted Touristville block (fixer bar, cheap eats, alley, strip-club entrance, fleabag motel).
- Two adjacent Barrens streets (the PC's apartment, a corner store, a gang hang).
- Canonical geographic anchors: **Snoqualmie River** (drains a third of the district), **flat terrain** with hills in the southern end, **Renton Corner Mall** as visible landmark.

## Hooks (design additions)

- **Tutorial vector.** Touristville fixer calls the PC cold. Low-stakes intro job leads into the district's broader web.
- **Multi-gang mosaic.** Six gangs share the Barrens; turf politics is the persistent faction substrate.
- **Mafia schism.** The O'Malley–Alamando regime vs. Del Secondi's surviving renegades is a live conflict the player can exploit.
- **Yakuza recruitment pipeline.** Promising street talent (warrior or magician) can be drawn into the Ill Squires. Runs against or for them are both plausible.
- **Supremacy vs. self-defense.** Humanis/KKK/Order vs. organized metahuman communities; runs that protect, sabotage, or expose either side.
- **Civic thread.** Mayor Gasston's recovery project is a vector for both corruption-exposure runs and corporate-adversary runs against those who want him to fail.
- **Poverty-driven runs.** Exploitation, debt, body-shopping, missing persons.
- **Glow City spectacle.** Visible skyline; occasional runs to the edge; full interior deferred to post-MVP.

## MVP notes

Concrete scope for the vertical slice (see `Meta/DESIGN - MVP.md`):

- **Geography:** Redmond Barrens only; Touristville strip as the one hand-built sub-zone.
- **PC start:** Low-tier apartment, 2,000¥/month rent due pressure.
- **Gangs:** all six (Halloweeners, Hellhounds, Spikes, Rusted Stilettos, Crimson Crush, Red Hot Nukes) present with turf.
- **Organized crime:** Seattle Mafia and Yakuza Rings ambient (black-market contacts, background events); no runs directly against them in MVP.
- **Supremacy groups:** ambient presence (rally events, hate-crime incidents, BBS chatter); metahuman-defense counter-presence in neighborhoods.
- **Named NPCs:** Gasston, O'Malley, Alamando, Autigerano — statted but peripheral to the first run.
- **First Johnson:** Touristville fixer with Connection ~3–4.
- **First run:** type **TBD**.
- **NPC procgen:** district metatype percentages + **neighborhood-level clustering** driven by the metahuman-self-defense pattern.
- **Police response:** canonical per-district override (4-man squads, Aero Citymaster / Nissan Patrol-1 vehicles).

## Open questions

- **First run content.** Retrieval / protection / extraction / sabotage — deferred decision.
- **Exact Touristville layout.** Street-level plan for the hand-crafted block.
- **Gang turf geography.** Specific blocks / streets owned by each of the six gangs.
- **Metahuman clustering geometry.** Which Redmond neighborhoods skew metahuman-heavy; needs author decision.
- **LTG Access Numbers** value (illegible in extract).
- **Shadowland post transcription** (p.127 and p.128 posts).
- **Metatype percentage 106% sum.** Keep canonical or renormalize for procgen? Currently retained as-is.
- **Corp factories.** Which corps actually run fortified facilities in Redmond? Unnamed in p.128; awaiting further extract.
- **Renton Corner Mall** detail — is it a destination, a run-target, or just a news-feed landmark in MVP?
