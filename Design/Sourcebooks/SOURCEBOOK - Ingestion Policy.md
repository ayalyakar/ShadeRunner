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

**By edition, then by book.** Example paths:

- `Design/Sourcebooks/SR1E/SOURCEBOOK - Core Rulebook.md`
- `Design/Sourcebooks/SR1E/SOURCEBOOK - Street Samurai Catalog.md`
- `Design/Sourcebooks/SR3E/SOURCEBOOK - Matrix.md`

Each book is a single file. Chapters become sections inside that file. If a
book grows too large to navigate in one file, it may be split into
`Sourcebooks/<Edition>/<Book Name>/SOURCEBOOK - NN Chapter Title.md`, with a
`SOURCEBOOK - Index.md` at the book level.

Edition folders use the compact abbreviation: `SR1E`, `SR2E`, `SR3E`, `SR4E`,
`SR4A`, `SR5E`, `SR6E`.

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

## Chapter note template

When a chapter is ingested, a section is added to the book's file using this
template. Keep the headers literal so every chapter looks the same.

```markdown
## Chapter NN — Chapter Title

**Status:** DRAFT | PARKED | QUESTIONING | CONFLICT | BLOCKED
**Ingested:** YYYY-MM-DD
**Pages:** NN–NN

### Raw quotes + page refs

> "Quotation from the book." (p. NN)

> "Another quotation." (p. NN)

### Paraphrased summary

Plain-language retelling of the chapter. Short paragraphs. Bulletable where
natural.

### Mechanical extracts

| Thing | Value | Notes |
| ----- | ----- | ----- |
| ...   | ...   | ...   |

Formulas, dice-pool rules, target numbers, modifiers, costs, etc.

### Design annotations

- How this should work in ShadeRunner.
- What feels dated or broken.
- What conflicts with other editions (link them).
- Seed ideas for downstream design docs.
```

## Workflow per chapter

1. You feed me a chapter: either the raw text, a summary, photos of pages,
   or a reference the I can fetch.
2. I produce the four-section note inside the book's file.
3. Status starts as `DRAFT`. It moves to `PARKED` once the note is "good
   enough for now" and `QUESTIONING` / `CONFLICT` / `BLOCKED` as needed.
4. New design seeds that emerge from the annotations get logged as open
   questions in the appropriate design section.
5. Repeat for next chapter.

## Starting queue

- [ ] `SR1E/SOURCEBOOK - Core Rulebook.md` — first book to ingest.

When you're ready, share the content for Chapter 1 (or whichever chapter you
want to start from — not all chapters need to be ingested in order) and I'll
produce the first four-section note.
