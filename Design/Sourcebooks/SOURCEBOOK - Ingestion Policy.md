# SOURCEBOOK - Ingestion Policy

This document governs how Shadowrun tabletop material is absorbed into
ShadeRunner's design notes. Ingestion is a continuous, chapter-by-chapter
activity that will run for the life of the project.

## Decisions

### Starting point

**SR1E (1989), chronological forward.** Ingestion begins with the original
Shadowrun First Edition core rulebook and walks forward through later editions
as we go. SR1E is the first canonical lens; SR2E / SR3E / SR4E / SR4A / SR5E /
SR6E layer on top, in order.

Branch sourcebooks (Matrix, magic, gear, regional, campaign) are ingested
after their edition's core rulebook, unless a design section explicitly needs
one earlier.

### Folder shape

**By edition, then by book.** Each book gets its own folder, and each
sub-topic inside that book gets its own file. Example paths:

- `Design/Sourcebooks/SR1E/Core Rulebook/SOURCEBOOK - Index.md`
- `Design/Sourcebooks/SR1E/Core Rulebook/SOURCEBOOK - Rolling the Dice.md`
- `Design/Sourcebooks/SR1E/Core Rulebook/SOURCEBOOK - Metahumanity Dwarf.md`
- `Design/Sourcebooks/SR1E/Core Rulebook/Images/IMAGE - Seattle Map 2050.png`
- `Design/Sourcebooks/SR3E/Matrix/SOURCEBOOK - Index.md`

Every book folder holds a `SOURCEBOOK - Index.md` that carries the
book-level metadata (publisher, year, designers, cover tagline) and the
chapter progress table, pre-populated from the book's ToC when available.
Any binary assets (maps, tables, art scans kept per the image policy below)
live in an `Images/` sub-folder at the book level.

Edition folders use the compact abbreviation: `SR1E`, `SR2E`, `SR3E`, `SR4E`,
`SR4A`, `SR5E`, `SR6E`. Book folders use Title Case with spaces
(`Core Rulebook/`, `Street Samurai Catalog/`).

### Ingestion granularity

**One note per sub-topic.** The unit of ingestion is the sub-topic as
printed in the book's ToC (e.g. "Rolling the Dice", "Condition Monitors",
"Cyberdecks", "The Hermetic Tradition"), not the major all-caps section
that groups them. Each sub-topic becomes its own markdown file named
`SOURCEBOOK - <Sub-topic Name>.md`.

The progress table in the book's Index groups sub-topics under their major
section headers for navigation, but each row tracks an independent file.

### Front matter

Book front matter (cover, credits, ToC itself) is **not** ingested as its
own note. The ToC's content lives in the book-level Index's progress
table.

**Exception:** canonical world-state art printed in front matter (most
notably: regional maps) is captured as its own standalone note, stored
alongside the other sub-topic notes in the book's folder. The Seattle
map in the SR1E Core Rulebook is the first example — see
`SR1E/Core Rulebook/SOURCEBOOK - Seattle Map 2050.md`.

### Visual assets

**Save originals + transcribe into text.** Maps, diagrams, tables, and
mechanical figures are both:

1. Stored as image files under the book's `Images/` folder, using the
   naming convention `IMAGE - <Descriptive Name>.<ext>`.
2. Transcribed into the relevant markdown note: legends, labels, and
   numbered entries become markdown tables; spatial relationships become
   prose; mechanical data becomes the standard four-section extracts.

Pure illustration / mood art (cover images, chapter splash art, character
portraits) is **not** saved to the repo — there is no design value in
binary art assets that have no mechanical or lore content. If a piece of
art does carry lore content (e.g. a named NPC's canonical appearance,
corporate logos for worldbuilding), it may be saved with a short rationale
in the accompanying note.

### Note content (every chapter entry gets all four)

Every chapter section in every sourcebook note carries these four
sub-sections, in this order:

1. **Raw quotes + page refs.** Direct quotations from the book with page
   numbers. Preserves source fidelity. Lets the original intent be
   re-verified later.
2. **Paraphrased summary.** Compressed retelling of the chapter in plain
   language. Fast to scan. Easy to cross-reference.
3. **Mechanical extracts.** Tables, formulas, dice pools, target numbers,
   modifiers, thresholds, costs, availability, essence losses, drain values,
   etc. — pulled out cleanly into markdown tables for future implementation
   reference.
4. **Design annotations.** My own notes: how this should work in ShadeRunner,
   what feels dated, what conflicts with other editions, what simulation
   depth is implied but not spelled out, what seed ideas this gives me.

Any of the four may be thin or empty for a given chapter (e.g. a
fiction-heavy chapter has no mechanical extracts), but all four headers
remain present so the structure is scannable.

### Conflict handling: timeline-aware

**Each edition is canon for its era.** When two editions disagree on a rule
or a piece of lore:

- SR1E rules / lore are canonical for 2050s-era in-game play.
- SR2E for late-2050s / early-2060s.
- SR3E for mid-2060s (Renraku Arcology, Matrix 2.0 transition, etc.).
- SR4E / SR4A for post-Crash-2.0, post-Emergence, the wireless-Matrix era.
- SR5E for mid-2070s.
- SR6E for 2080s-forward.

Mechanical rules, tech, lore, and world-state all drift with the in-game
year. A runner with a 25-year career legitimately plays across multiple
rulesets — this is not a bug; it is simulation depth.

When editions genuinely contradict (not just era-drift, but "this fact is
different"), the later edition's retcon stands only from its publication
year forward. Earlier state remains canonical to earlier play.

## Sub-topic note template

When a sub-topic is ingested, a new file is created at
`Sourcebooks/<Edition>/<Book Name>/SOURCEBOOK - <Sub-topic Name>.md` using
this template. Keep the headers literal so every note looks the same.

```markdown
# SOURCEBOOK - <Sub-topic Name>

**Edition:** SR?E
**Book:** <Book Name>
**Major section:** <All-caps section this sub-topic belongs to>
**Pages:** NN–NN
**Status:** DRAFT | PARKED | QUESTIONING | CONFLICT | BLOCKED
**Ingested:** YYYY-MM-DD

## Raw quotes + page refs

> "Quotation from the book." (p. NN)

## Paraphrased summary

Plain-language retelling. Short paragraphs. Bulletable where natural.

## Mechanical extracts

| Thing | Value | Notes |
| ----- | ----- | ----- |
| ...   | ...   | ...   |

Formulas, dice-pool rules, target numbers, modifiers, costs, etc.

## Design annotations

- How this should work in ShadeRunner.
- What feels dated or broken.
- What conflicts with other editions (link them).
- Seed ideas for downstream design docs.
```

## Workflow per sub-topic

1. You feed me a sub-topic: either the raw text, a summary, photos of
   pages, or a reference I can fetch.
2. I create `SOURCEBOOK - <Sub-topic Name>.md` in the book's folder, fill
   in the four sections, and flip the matching row in the book's
   `SOURCEBOOK - Index.md` progress table from `QUESTIONING` to `DRAFT`.
3. Status moves through `DRAFT` → `PARKED` (good enough for now) over time,
   or into `CONFLICT` / `BLOCKED` as needed.
4. New design seeds that emerge from the annotations get logged as open
   questions in the appropriate design section.
5. Repeat for next sub-topic. Order is flexible — out-of-order ingestion
   is supported.

## Starting queue

- [x] `SR1E/Core Rulebook/SOURCEBOOK - Index.md` — book scaffold with full
      ToC progress table (all rows `QUESTIONING`).
- [x] `SR1E/Core Rulebook/SOURCEBOOK - Seattle Map 2050.md` — Seattle map
      note (partial; legend awaits higher-res scan).
- [ ] First sub-topic ingestion from SR1E Core Rulebook — awaiting content.

When you're ready, share the content for any sub-topic in the progress
table and I'll produce the note.
