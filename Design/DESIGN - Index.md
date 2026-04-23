# ShadeRunner — Design Index

Solo-developed, NSFW-forward Shadowrun-1E-leaning CRPG set in Seattle 2050–2064. This index links every design document and summarizes its domain. Each file captures **decisions** made so far, **rationale** where useful, and **open questions** for later passes.

## Conventions

- One file per domain. Filenames follow `DESIGN - Name.md`.
- Folders start with a capital letter (e.g. `Technology`, `World`).
- Decisions are marked **DECIDED**; unresolved items are under **Open questions**.
- If a decision later changes, edit the file in place and note the change under **Revisions**.
- Canonical data (lore, stats, places) lives in `Data/`. Design docs reference Data by path.
- Source material (sourcebook page images) lives in `Sources/`. Data files cite `Sources/` images.

## Top level

- [DESIGN - Vision.md](DESIGN%20-%20Vision.md) — pitch, pillars, what the game is and isn't.
- [DESIGN - Production.md](DESIGN%20-%20Production.md) — solo time budget, risks, milestones.

## Setting

- [Setting/DESIGN - Canon.md](Setting/DESIGN%20-%20Canon.md) — source policy (SR1E primary, later rulings where cleaner), era drift 2050–2064, Seattle Sourcebook as primary source.

## Meta

- [Meta/DESIGN - MVP.md](Meta/DESIGN%20-%20MVP.md) — MVP scope: full-run vertical slice, Redmond, all four archetypes.
- [Meta/DESIGN - NSFW.md](Meta/DESIGN%20-%20NSFW.md) — adult-content policy and pillar framing.

## Gameplay

- [Gameplay/DESIGN - Core Loop.md](Gameplay/DESIGN%20-%20Core%20Loop.md) — run-for-hire loop.

## Narrative

- [Narrative/DESIGN - Writing.md](Narrative/DESIGN%20-%20Writing.md) — three-layer writing pipeline + BBS persona policy.

## Character

- [Character/DESIGN - Creation.md](Character/DESIGN%20-%20Creation.md) — karma point-buy chargen; all 5 metatypes; all 4 archetypes.
- [Character/DESIGN - Metatypes.md](Character/DESIGN%20-%20Metatypes.md) — Human, Elf, Dwarf, Ork, Troll. Stats + world reactivity.
- [Character/DESIGN - Cyberware.md](Character/DESIGN%20-%20Cyberware.md) — minimal MVP catalogue; Essence economy.

## Systems

- [Systems/DESIGN - Combat.md](Systems/DESIGN%20-%20Combat.md) — phase-pass initiative, square grid, SR1E d6 exploding dice, Physical + Stun tracks.
- [Systems/DESIGN - Matrix.md](Systems/DESIGN%20-%20Matrix.md) — abstract minigame, SR1E wired Matrix baseline, wireless post-MVP drift.
- [Systems/DESIGN - Magic.md](Systems/DESIGN%20-%20Magic.md) — Hermetic + Shamanic MVP; Spellcasting + Summoning; Adept power tree.

## Technology

- [Technology/DESIGN - Engine.md](Technology/DESIGN%20-%20Engine.md) — Godot 4 + GDScript + 3D isometric.
- [Technology/DESIGN - AI Tooling.md](Technology/DESIGN%20-%20AI%20Tooling.md) — dev-time LLM yes, runtime never.

## Pending (to be added as decisions land)

- Character — Progression, Aging, Lifestyle, Downtime
- Systems — Rigging (post-MVP)
- World — Economy, Factions, Simulation, Time, Reputation, Procgen
- Presentation — Art Direction, Audio, UI
- Social — Contacts
- Setting — Districts / Redmond (lands when the Seattle Sourcebook's Redmond chapter is ingested)

## Status

Foundational pass in progress. Scoping decisions made; system-specific design (combat math, chargen, magic, Matrix, NSFW pipeline) pending.
