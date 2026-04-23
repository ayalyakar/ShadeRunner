# DESIGN - Canon

## Decision

**DECIDED:** Canon is rooted in **Shadowrun 1E** (FASA, 1989–1990 era) with **later-edition rulings adopted where they are cleaner** to implement. Era spans **2050–2064** (free drift — the campaign can reach Crash 2.0, but era transitions are not mechanically simulated at MVP).

## Source policy

- **Primary source:** SR1E rulebooks and sourcebooks. The **Seattle Sourcebook** (FASA, 1990) is the primary lore anchor for this project.
- **Secondary sources:** SR2E, SR3E, SR4, SR5 when they clarify mechanics that SR1E leaves rough, or when they extend canon in ways the project wants.
- **Contradiction arbiter:** when SR1E and a later edition disagree on *lore*, the project defaults to the **later edition** for mechanical cleanliness — but we retain SR1E voice and period feel. Lore contradictions are case-by-case; log them in the relevant data file's `revisions:` field.

## Era drift

- **Start:** 2050 (the Seattle Sourcebook's year).
- **Reach:** up to 2064 (includes Crash 2.0 as a potential canonical event the player can witness).
- **MVP:** era is locked at 2050. No transitions simulated in MVP.
- **Post-MVP:** era-transition system (pre-built canonical events, adjusting NPC rosters, corp landscapes, tech availability, Matrix state).

## Canon storage

- **Per-metroplex:** `Data/Lore/Metroplex/<Name>.yaml` (Seattle-wide climate, travel, economy-tier framework, history, etc.).
- **Per-district:** `Data/Lore/Districts/<District>.yaml`.
- **Per-neighborhood:** `Data/Lore/Districts/<District>/<Neighborhood>.yaml`. Neighborhoods live as sub-folders under their parent district; the district's yaml carries the neighborhood index.
- **Per-faction:** `Data/Lore/Factions/<Name>.yaml`. Syndicate / gang / corp **turf lives on the faction side** (a `turf:` list referencing district + neighborhood files). Neighborhood files may mention the syndicate for cross-reference but the authoritative list is on the faction.
- **Per-NPC:** `Data/Lore/NPCs/<Name>.yaml`.
- **Per-place:** `Data/Lore/Places/<Type>/<Name>.yaml` (Hotels, Restaurants, Bars, Brothels, Clinics, etc.).
- **Per-landmark:** `Data/Lore/Places/Landmarks/<Name>.yaml` (Queen Anne Hill, Space Needle, Kingdome, mountains, etc.). Landmarks are named-anchor places with canonical significance but often no internal "venue" the PC visits.
- **Other canon artifacts:** `Data/Lore/<Kind>/…` as needed (Corporations, Magical Traditions, Gear, etc.).

## Source citation

Every canonical claim should cite a source. Format:

```yaml
sources:
  - edition: SR1E
    book: "Seattle Sourcebook"
    year: 1990
    page: 131
    image: "Sources/SR1E-Seattle/p131.png"   # optional but preferred
    section: "Redmond / Crime"
```

## Fidelity policy

- **Structured facts + prose notes.** Extract numeric facts (population, security rating, etc.) and entity lists (NPCs, businesses) into structured fields. Keep flavor prose as human-readable notes in the same file.
- **Verbatim prose** is not required. Summarize and cite.
- **Transcription uncertainty** is flagged with `transcription_note:` on the affected field.
- **Seed, not scripture.** Canon is a starting point to calibrate against gameplay, not a straitjacket. When canon and gameplay conflict, gameplay wins; note the deviation.

## Authored canon

- Content the project authors (NPCs, places, runs, BTL chips, NSFW content) that does not exist in any published source is marked `authored: true` in the data file.
- Authored canon is held to the same structural standards as transcribed canon (stats, relationships, hooks).

## Revisions

When a canonical decision changes, edit the file in place and log it:

```yaml
revisions:
  - date: 2026-04-23
    change: "Treaty of Denver year corrected from 2018 to 2017 per SR3E."
    source: "SR3E core, p.42"
```

## Open questions

- Matrix canon post-Crash 2.0 — SR4's wireless Matrix breaks SR1E assumptions. How do we represent the transition?
- Magic awakening year and world-history alignment across editions.
- Awakened beings, metatype variants, critter lists — which edition's taxonomy is canonical?
- When authoring NSFW canon (brothels, BTL studios, specific chips), do we attribute to a canonical corp or to an authored actor?
