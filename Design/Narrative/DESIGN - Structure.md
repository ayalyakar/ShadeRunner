# DESIGN - Structure

## Decision

**DECIDED:** Three narrative layers co-exist:

1. **Strong authored main plot** — a hand-crafted overarching story with chapters (Dragonfall / Hong Kong scale).
2. **Multiple self-contained campaign arcs** — several mid-length arcs the player can pick up, stumble into, or ignore.
3. **Meta-arc from decade transitions** — surviving / participating in canonical events (Crash 2.0, NeoNET fall, Dunkelzahn era, SOX, Dragon civil war) as its own running story.

Note: "emergent only" is **not** chosen — there will always be authored plot. But runs can also be fully emergent (see `Gameplay/DESIGN - Core Loop.md`).

## Main plot

- A central story with a handful of chapters.
- Drives player trajectory from "fresh runner in Redmond Barrens" to "operator with continental consequence".
- Tied to player choice and faction state; no linear path.
- Ends (per arc) are real — resolutions can change the world (faction collapses, canonical events diverted within canon-flex rules).

## Campaign arcs

- 4–8 standalone arcs, each ~the length of a small SR campaign book.
- Each arc focuses on a theme / faction / region (e.g., "Ancient Elves of Tír Tairngire", "Yakuza succession war", "Mage Society purge", "Rigger-gang insurgency").
- Arcs can be played in any order, sometimes interleave, sometimes conflict.
- Arcs use hand-authored set pieces with procgen filler for the connective tissue.

## Meta-arc (the timeline itself)

- Canonical events fire over the decades (see `Setting/DESIGN - Timeline.md`).
- The player's relationship to these events — witness, participant, agent — is itself a story.
- Long-running PCs accumulate a personal relationship with the 6th World's history.
- Retrospective moments: "the kid runner who was there for Crash 2.0".

## Writing volume

The three layers have different writing densities:

| Layer | Hand-written | Templated | LLM-assisted authoring |
|---|---|---|---|
| Main plot | High | Low | Medium (drafts to edit) |
| Campaign arcs | Medium-high | Medium | Medium |
| Meta-arc events | Medium | High | High |
| Side runs | Low | High | High |
| Ambient (BBS, news, NPC lines) | Minimal | Very high | High |

See `Narrative/DESIGN - Writing.md` for the authoring pipeline.

## Choice & consequence

- Every arc has meaningful choice points with permanent outcomes.
- Choices interact with the sim — a faction collapse from an arc propagates to the sim layer.
- Arcs can "lock" others or open them.
- Long-term reputation and canon-flex state is derived from accumulated choices.

## Open questions

- How much does the main plot constrain the sim, and vice versa?
- Arc pacing with the player's ability to skip decades.
- Replayability vs. authored specificity — same arcs across characters?
- Narrative voice — is there a narrator, or strictly character-POV?
