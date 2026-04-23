# DESIGN - Production

## Context

- **Team:** solo developer.
- **License / IP:** personal use only; no commercial distribution; no censoring constraints.
- **Time budget:** 10–20 hrs/week (serious side project). Implies a 5–7 year realistic horizon to a satisfying state, and likely *indefinite* ongoing development.

## Top risks (all acknowledged)

1. **Sim performance at scale.** DF/RimWorld-tier NPC simulation across a full sprawl stresses CPU and memory. Mitigation: zonal persistence, LODed simulation, custom sim backend via GDExtension if needed.
2. **Content volume.** A solo dev cannot hand-author enough lines, assets, and quests for the promised scope. Mitigation: LLM-assisted authoring, templated ambient, procedural generation for districts/NPCs/side runs/loot; hand-craft only hero content.
3. **Systems interlock & balance.** Matrix + Magic + Combat + Social + Rigging all interacting is a combinatorial nightmare. Mitigation: build each subsystem to a unified resolution model (see `Systems/DESIGN - Combat.md`); prototype slices before integration.
4. **Finishing at all.** The project is existentially scope-creep-prone. Mitigation: MVP-first (see `Meta/DESIGN - MVP.md`); every feature must fit the MVP or be deferred; explicit "later" backlog, not inline implementation.

## Scope-management philosophy

- **Ship the MVP before expanding anything.** A playable Redmond-Barrens street-sam vertical slice is the one gate.
- **Every system has a v1 (playable), v2 (deep), v3 (systemic).** Ship v1 across all systems before v2 on any.
- **Defer aggressively.** New cool ideas go to `Design/` as open questions, not into code.
- **Hand-authored content is expensive.** Always prefer templated / procedural / LLM-assisted authoring before writing something manually.

## Milestones (rough)

| # | Name | Target | Gate |
|---|------|--------|------|
| 0 | Project setup | Repo, engine, CI, save scaffold | Can run empty Godot project |
| 1 | Character sheet | Chargen (point-buy) + stat model | A valid SR char in JSON |
| 2 | Combat slice | Phase-pass turn-based against a single opponent | Street-sam can beat a gang mook |
| 3 | District slice | One neighborhood of Redmond Barrens, navigable | Can walk/drive in a district |
| 4 | Run structure | Johnson meet → legwork → execute → payout | One scripted run completes |
| 5 | Contacts v1 | Loyalty/Connection, one fixer, one mentor | Can hire legwork help |
| 6 | Matrix stub | Skill-gated checks (no 3D layer yet) | Hack a maglock in a run |
| 7 | Lifestyle v1 | Rent, food, heat, day/night clock | Survive a month between runs |
| 8 | **MVP** | Above integrated, one full run type end-to-end | **Shippable to self** |

Beyond MVP: magic, rigging, astral, full NPC simulation, multi-district, multi-city, decade transitions. Each is a multi-month chunk.

## Open questions

- Which subsystem to build *second* after MVP: Magic, Matrix 3D layer, or rigging?
- Do I want a playtesting group (even just friends) or is this fully private forever?
- How much of the simulation can run on a single background thread vs. needing a separate process?
