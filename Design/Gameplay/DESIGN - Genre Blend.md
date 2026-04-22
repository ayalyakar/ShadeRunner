# DESIGN - Genre Blend

## Decision

**DECIDED:** The game blends many genres rather than committing to one. Explicit **yes** and **no** lists below.

## Included genres

- **Immersive sim** — systemic interactions, multiple solutions per obstacle, emergent gameplay (Deus Ex / Prey feel).
- **Life / city simulation** — NPCs have routines, relationships, goals; economy and weather and news simulated.
- **Solo-character RPG** — one PC; no party control.
- **Detective / investigation** — clue-boards, forensic evidence, interviews, deduction (LA Noire / Disco Elysium).
- **Survival / lifestyle management** — food, sleep, mood, rent, essence, injury recovery.
- **Narrative / branching fiction** — dialogue-heavy scenes, skill checks, consequence (Disco Elysium / Citizen Sleeper).
- **Roguelite structure** — run failure can cascade into character-ending consequences (see `Character/DESIGN - Aging.md` for the protagonist-switch escape valve).
- **Tactical turn-based combat** — SR phase/pass initiative (see `Systems/DESIGN - Combat.md`).

## Excluded genres

- **Party-based tactics** — no BG3/XCOM-style party control. Other runners are NPCs.
- **Grand strategy / crew management** — the PC is not a crew boss. No X-COM geoscape layer.
- **Multiplayer / co-op / MMO** — single-player only (see `Meta/DESIGN - Multiplayer.md`).
- **Single-tone** — no imposed tone; emergence produces the tone.

## Blend strategy

- Each genre is not a mode but a **lens**. The player is always in the sim; the UI, controls, and available actions shift to foreground the appropriate genre in the active scene.
- Combat: tactical + immersive sim.
- Downtime: life sim + survival + narrative.
- Legwork: detective + narrative + social engineering.
- Long arc: roguelite consequence + generational / legacy character potential.

## Risks of the blend

- Jack-of-all-trades / master-of-none feel. Mitigation: each genre implemented with real depth; none of them are a veneer.
- UX complexity from too many genres in one game. Mitigation: context-dependent UI (see `Presentation/DESIGN - UI.md`).
- Content cost across genres. Mitigation: solo-realism + procgen (see `Design/DESIGN - Production.md`).

## Open questions

- Should detective minigames be mandatory for investigation runs or skippable via high skill?
- How much survival pressure is too much before it feels like a chore?
- Roguelite degree: is a full run-ending death ever default, or always opt-in?
