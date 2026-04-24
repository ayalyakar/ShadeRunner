# Sources

Raw sourcebook page screenshots cited by files in `Data/`.

## Layout

`Sources/<Edition-and-Book>/pNNN-<slug>.png` — one file per page. Page numbers are the *printed* sourcebook page numbers, not the scan's image index.

## Current archive

### SR1E-Seattle (Shadowrun 1E — Seattle Sourcebook, FASA, 1990)

- `p001-cover.png` — cover.
- `p002-toc-1.png` — Table of Contents, page 1 of 3.
- `p003-toc-2.png` — Table of Contents, page 2 of 3.
- `p004-toc-3.png` — Table of Contents, page 3 of 3.
- `p005-introduction.png` — Introduction chapter opener.

### SR1E-QueenEuphoria (Shadowrun 1E — Queen Euphoria adventure module, FASA, 1990)

- `p001-cover.png` — cover (dragonfly motif, title only).
- `p002-credits.png` — title page / credits / FASA copyright 1990 / publisher address (archive-only; credits deliberately not ingested to canon per project policy).
- `p003-toc-prologue-open.png` — Table of Contents + opening of the "Ant Lion: A Prologue" fiction. TOC ingested as the module structural skeleton; prologue prose is archive-only.
- `p004-prologue-continued.png` — "Ant Lion: A Prologue" (continued). Archive-only per project policy; no canon stubs for prologue-only entities (Dorin, Daniels, Alex the Coyote shaman, the Ant Lion creature, the pyramid/temple).
- `p005-prologue-end.png` — "Ant Lion: A Prologue" (final page of prologue fiction). Archive-only. **Note on file naming:** the `pNNN` prefixes in this sub-archive track **screenshot-upload order**, not strictly printed page numbers - because the phone-scanner screenshots bleed across page boundaries, the 7 screenshots `p001`-`p007` cover printed pages 1-6. The adventure YAML's per-source `page:` field is authoritative for printed-page cross-references.
- `p006-introduction.png` — **printed p.5**: INTRODUCTION chapter opener + Gamemastering Notes + Making Success Tests + How To Use This Book (columns). GM-facing module conventions. Fully ingested into adventure YAML as `presentation_conventions`, `adaptation_notes`, and `setting_recap_from_p5`.
- `p007-plot-synopsis.png` — **printed p.6**: tail of How To Use This Book (Cast of Characters / Picking Up The Pieces / Player Handouts paragraphs) + full PLOT SYNOPSIS. Ingested as structured `plot_beats` (16 beats), with new `npc_refs` / `faction_refs` / `place_refs` / `creature_refs` entries for Thomas Dorin (Craft), Euphoria, Ludomeria, Elliot Whitecastle, Pride, Van Willis, Sirius Foods, Garnaty's Bar, Euphoria's penthouse, the Amber Gel / Hive facility, Queen Ant Spirit, and Soldier/Worker Insect Spirits. Spoiler-gated where appropriate.
- `p008-wake-up-call.png` — **printed p.8**: first scene of The Adventure. Ellery Whitecastle (local Fixer, hired by Ludivenko Corporation) places a videophone call to the PC and brokers a meet with a Ludivenko "Mr. Johnson" at Pier 36, Tacoma docks, 11pm. Fully ingested: `scenes[].wake_up_call` block on the adventure YAML plus new files `Data/Lore/NPCs/Ellery Whitecastle.yaml`, `Data/Lore/NPCs/Mr. Johnson (Ludivenko, Queen Euphoria).yaml`, `Data/Lore/Factions/Ludivenko Corporation.yaml`, and `Data/Lore/Places/Docks/Pier 36 (Tacoma).yaml`. This page also reconciles two p.6 low-res misreads: `Elliot Whitecastle` → `Ellery Whitecastle`, and `Ludomeria` → `Ludivenko Corporation` (both superseded entries preserved with `supersedes_with` pointers).
- `p009-off-and-running.png` — **printed p.9**: second scene of The Adventure (*Off and Running*; the p.3 TOC's "Road West?" was a low-res misread and is silently corrected). Tell It To Them Straight — pier-at-night arrival cadence, Mr. Johnson on-screen debut, the kidnap brief, fee and terms.
- `p010-off-and-running-behind.png` — **printed p.10**: *Off and Running* Behind the Scenes + Debugging. Full negotiation stats (Opposed Negotiation, 20,000¥ base ±1,000 delta, fixed half/half payment plan), Juan Diablo introduction with equipment + SR1E stat refs (Company Man p.164, Troll Street Samurai p.46), keycard handoff for Royal Meadows Apartments, whispernumber #5-5-Chrome. New files: `Data/Lore/NPCs/Juan Diablo.yaml`, `Data/Lore/Places/Apartments/Royal Meadows Apartments.yaml`, `Data/Lore/Products/Amber Gel.yaml` (opens new `Products/` tree). Adventure YAML gains the `scenes[].off_and_running` block, a new `products_refs` block, and `sr_rules_refs` structured citations on Mr. Johnson / Diablo / Whitecastle files.

## Citation format (in `Data/` YAML)

```yaml
sources:
  - edition: SR1E
    book: "Seattle Sourcebook"
    year: 1990
    page: 131
    image: "Sources/SR1E-Seattle/p131-redmond-crime.png"
    section: "Redmond / Crime"
```
