# DESIGN - Index

This is the top-level map of ShadeRunner's design documentation. Everything
under `Design/` is a living document. Nothing here is final. Nothing here is
promised to ship.

## How this doc set is organized

- **`Design/`** — all design documentation lives here.
- **Sub-folders** use `Title Case` with spaces (`Character Systems/`,
  `Matrix Pillar/`). Each word capitalized, no kebab, no camel, no snake.
- **Files** follow the pattern `CATEGORY - Name.md`:
  - Uppercase category prefix (`DESIGN`, `LORE`, `SYSTEM`, `SOURCEBOOK`).
  - ` - ` separator (space, dash, space).
  - Title-case human-readable name (`Vision`, `Core Loop`, `Matrix Overview`).
- Sub-folders get their own index file when they grow past a handful of docs.

## How this doc set evolves

1. **Question-driven.** Before a section is written, the author answers a
   round of design questions. Nothing gets written from silent assumption.
2. **Section-by-section.** Sections are opened, questioned, drafted, and
   parked. They are revisited whenever new sourcebook material or new design
   insight warrants it.
3. **Sourcebook ingestion is continuous.** Tabletop material is fed into the
   design chapter by chapter, edition by edition, for the life of the project.
   Sourcebook-derived notes live under `Sourcebooks/` (to be created when
   ingestion begins).
4. **Forever-in-development.** There is no deadline. Depth beats breadth.

## Current contents

- `DESIGN - Vision.md` — elevator pitch, player fantasy, north stars,
  non-goals, inspiration, working style. **Start here.**
- `DESIGN - Index.md` — this file.
- `Sourcebooks/` — sub-topic-level ingestion of the Shadowrun tabletop
  material. Starts with SR1E, expands forward through 6E. One file per
  sub-topic as printed in each book's ToC; one `SOURCEBOOK - Index.md` per
  book.
  - `SOURCEBOOK - Ingestion Policy.md` — starting edition, folder shape,
    sub-topic granularity, note-content standard, timeline-aware conflict
    rule, visual-asset policy, sub-topic note template.
  - `SR1E/Core Rulebook/SOURCEBOOK - Index.md` — first book in the queue;
    ToC-populated progress table (~307 rows, all `QUESTIONING`).
  - `SR1E/Core Rulebook/SOURCEBOOK - Seattle Map 2050.md` — Seattle map
    note (partial; legend needs higher-res scan).
  - `SR1E/Core Rulebook/Images/` — binary assets (maps etc.) kept
    alongside their sub-topic notes.

## Planned top-level sections (not yet written)

The list below is a placeholder. None of these exist yet. Each will be opened
with its own question round before any content is drafted.

- `DESIGN - Scope.md` — what's in, what's out, what's deferred.
- `DESIGN - Pillars.md` — the per-pillar depth targets (Magic, Matrix,
  Rigging, Combat, Social, Crafting, Economy, Medical, etc.).
- `DESIGN - Timeline.md` — Sixth-World canon events the sim must honor.
- `DESIGN - Core Loop.md` — moment-to-moment, job-to-job, year-to-year loops.
- `Character Systems/` — metatypes, priorities, karma, aging, cyberware,
  essence, awakening, qualities, lifestyle, progression.
- `World Systems/` — factions, corps, geography, economy, law, canon events.
- `Pillar - Matrix/` — full-depth Matrix subsystem design.
- `Pillar - Magic/` — full-depth magic subsystem design.
- `Pillar - Rigging/` — full-depth rigging subsystem design.
- `Pillar - Combat/` — full-depth combat subsystem design.
- `Pillar - Social/` — full-depth social subsystem design.

## Status legend (for use inside individual docs)

- **DRAFT** — actively being written.
- **PARKED** — good enough for now, will be revisited.
- **QUESTIONING** — in active question-round, no content yet.
- **CONFLICT** — multiple editions / sources disagree, needs a call.
- **BLOCKED** — waiting on another section's decisions.
