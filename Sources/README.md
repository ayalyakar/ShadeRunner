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
