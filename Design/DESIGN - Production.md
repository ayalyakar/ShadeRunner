# DESIGN - Production

## Framing

**Solo developer, personal project, no ship date.** This game exists to be built and played by one person (and that person's chosen audience). There is no publisher pressure, no external backer, no marketing calendar.

That framing is both freeing and dangerous:

- **Freeing:** no scope compromises for market fit. NSFW unlock. No localization. No accessibility compliance floor. Windows-only.
- **Dangerous:** no external forcing function for ship discipline. The project dies if scope outruns time, and there's no one to say "cut feature X."

## Scope-vs-time risk (logged)

The decided scope is ambitious for solo:

- 50+ hour main path.
- All four SR archetypes playable at MVP (combat + Matrix + magic + [rigging later]).
- Character creation, blank slate.
- Era drift 2050–2064 (14 in-game years canonically reachable).
- Illustrated-explicit NSFW pipeline.
- Full 3D-rendered isometric in Godot.
- Turn-based combat engine from scratch.
- Seattle metroplex canon ingestion.

**Risk:** the ambition lives or dies on MVP discipline. If MVP sprawls, nothing else ships.

**Mitigation (DECIDED):**

- MVP is a **full-run vertical slice**, not a content-rich beta. One neighborhood, one Johnson, one run. Every subsystem exists at minimum viable depth, then grows.
- District locked to **Redmond** for MVP. Other districts are stubs in Data/ until MVP ships.
- Each SR archetype must be playable end-to-end in MVP, but each starts with a small verb set (one combat archetype role per archetype, not full tree). Post-MVP passes expand.
- Everything canonical lives in `Data/` before it lives in the engine. Lore + stats decoupled from code.

## Discipline principles

- **No feature without a ship plan.** Every pillar has a "what does MVP-depth look like" note before implementation starts.
- **No abstraction without two call sites.** If a system has only one user, don't generalize it yet.
- **Data before engine.** Canon and systems data are authored before scene-level scripting. The Godot project reads from `Data/`.
- **Markdown decisions.** Every meaningful decision lands in a `Design/` file before code changes.
- **Sources cited.** Lore claims reference `Sources/` images. No lore without a citation unless flagged as authored.

## Time budget

Not committed to a calendar. The project proceeds when time allows. The ingestion-and-design phase is expected to take substantially longer than any commercial equivalent; that is fine.

## Milestones (ordered, not dated)

1. **Foundation pass.** Design scaffold + source archive pipeline. *(Current phase.)*
2. **Redmond canon ingestion.** Seattle Sourcebook's Redmond chapter fully in `Data/`. Other districts stubbed.
3. **Combat engine v0.** Playable, dice-pool-correct, solo PC vs. simple opponents, one Redmond neighborhood tile.
4. **Chargen v0.** All four archetypes selectable, minimum stats / skills / gear.
5. **First-run vertical slice.** Meet → Legwork → Execute → Payout, shipped through one complete run.
6. **MVP.** Any archetype plays the vertical slice end-to-end, including the NSFW pipeline on a relevant scene.
7. **Post-MVP:** rigging; additional districts; era-transition system; more runs.

## Open questions

- Do we ever do a pre-MVP tech demo (combat-only) to derisk Godot scoping earlier?
- What's the acceptance test for "this feels like SR"?
- How much of the NSFW art pipeline (diffusion prompts → curation → shipping) needs a tool built around it?
- Save migration strategy across in-development format changes — just break saves, or migrate?
