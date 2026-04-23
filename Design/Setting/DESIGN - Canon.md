# DESIGN - Canon

## Decision

**DECIDED:** Strictly canonical lore baseline, with a **hybrid branching policy**:

- Most canonical events occur **unless the player acts**. The default world runs on canon.
- A core set of **anchor events are unstoppable** regardless of player action — they are structural to the 6th World (e.g. Crash 2.0, major dragon events, SOX).
- Beyond those anchors, timelines can **diverge** through both player influence and autonomous faction/world behavior.

## Canon fidelity principles

- Names, dates, factions, famous NPCs follow published sourcebooks across SR1E–SR6E.
- Geography and district character follow canon.
- Magic, metatype, and technology rules follow canon as much as the hybrid mechanics allow.
- Where sources conflict between editions (they often do), the latest edition covering that detail wins unless the earlier version is mechanically better.

## Anchor events (draft list, needs expansion)

These fire regardless of the player:

- **2011** — Awakening (pre-game in any campaign).
- **2039–40** — Night of Rage.
- **2057** — Great Ghost Dance aftermath, Dunkelzahn's election and assassination.
- **2064** — Crash 2.0 (Matrix restructured).
- **Ongoing** — Corporate Court reshuffles, AAA corp mergers/splits on canonical dates.

## Canon-unless-player-acts examples

These can be altered by the player:

- Specific named NPC deaths (if the player protects them).
- Particular corp facility ownership (if the player runs against it).
- A contact's canonical fate (if the player hires, betrays, or shelters them).
- District control shifts if the player arms or weakens a gang.

## Research & documentation

- Each anchor event and altered-by-player event gets an entry in a lore database (to be created).
- Sourcebook references accompany each entry.
- Conflicts between editions are flagged and a policy recorded.

## Sourcebook ingestion

Canonical extracts (fact sheets, NPC statblocks, faction entries, event descriptions) flow into the project via a **transcribed data + design reference** pipeline.

### Policy

- **Seed, not truth.** Extracts seed the game; numbers may be rebalanced for playability. Each rebalance is documented at the point of use.
- **Edition attribution required.** Every transcription records its source edition and page. SR1E data and SR6E data are both canonical — neither supersedes the other by default.
- **Edition-conflict reconciliation:** when multiple editions cover the same entity with different numbers, a per-entity policy is recorded (latest wins / oldest wins / per-stat merge / our own calibration). Default: **latest edition wins for stats, earliest-canonical wins for lore**, overridable per entity.

### Storage

- **Transcribed stats / data** → `Data/Lore/<domain>/<name>.yaml`
  - `Data/Lore/Districts/` — district fact sheets.
  - `Data/Lore/NPCs/` — canonical NPC statblocks / personas.
  - `Data/Lore/Factions/` — corps, gangs, organizations.
  - `Data/Lore/Places/` — location entries, sub-categorized by type:
    - `Data/Lore/Places/Hotels/`
    - `Data/Lore/Places/Restaurants/`
    - (more type sub-folders as they arrive — shops, clubs, safehouses, clinics, lodges.)
- **Design prose** → `Design/Setting/<domain>/DESIGN - <Name>.md`
  - `Design/Setting/Districts/DESIGN - <District>.md` — district design sheets (hybrid template).
- **Source images / scans** are not committed to the repo; the transcribed data files are the authoritative in-repo reference.

### District template (sourcebook-tab hybrid)

Per-district design files use the sourcebook tab layout (**Facts, History, Downtown, Outlying, Government, Economy, Crime, Maps**) extended with design-only sections (**Hooks, MVP Notes, Open Questions**). See `Design/Setting/Districts/DESIGN - Redmond.md` for the reference implementation.

### Historical events split

Per-district history events split cleanly:

- **Pre-game events** (dated before the campaign start year) are **backdrop only** — referenced in dialogue, BBS, news archives, but not simulated.
- **In-game-period events** are **scheduled sim events** in the event log (see `Technology/DESIGN - Persistence.md`) and fire at their canonical dates subject to the canon-vs-branching policy above.

### Shadowland BBS posts

Quoted Shadowland posts in extracts are ingested **verbatim** as in-game BBS content attributed to their canonical handles. This forms a seed corpus for the BBS system; additional posts can be authored in the same voice (see `Narrative/DESIGN - Writing.md`).

## Open questions

- Where exactly is the line between "anchor" and "can be altered"? Needs a full pass through the canonical timeline.
- How do anchors feel to the player when they're right in the middle of one — loss of agency risk.
- If the player time-shifts forward, do altered-by-them events retroactively re-canonicalize?
- How much "what if" alt-history is surfaced in-world when the player diverges heavily?
