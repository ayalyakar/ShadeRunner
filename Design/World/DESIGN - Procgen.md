# DESIGN - Procgen

## Decision

**DECIDED:** Procedural generation is used for **minor NPCs, interiors, side runs, and loot/gear/contract variants**. Hero content (main arcs, key contacts, signature locations) is hand-authored. All procgen uses seeded RNG keyed to stable entity IDs for determinism.

## Targets

### Minor NPCs
- Identity, metatype, appearance, profession, schedule, dwelling, social graph.
- Templates per district (Redmond Barrens barfly templates differ from Downtown exec templates).
- Promoted to "named minor" on player interaction; identity persists.
- **Demographic distributions are authoritative** — metatype mix, education levels, corp-affiliation rate, and income distribution are read directly from the district's canonical fact sheet (`Data/Lore/Districts/<Name>.yaml`). Procgen must honor these ratios when sampling a district's population.
- **Neighborhood-level clustering overrides flat distributions.** Some districts carry a canonical clustering rule in their data file (e.g. Redmond's post-Night-of-Rage metahuman self-defense clustering, p.128). When present, procgen samples metatype by neighborhood using the clustering rule rather than flat district-wide ratios. Sub-district overrides take precedence but cannot contradict the district baseline's totals.

### Interiors (apartments, shops, corp offices, hideouts)
- Room-graph generator: pick archetype (e.g. "middle-class apartment"), place rooms from a palette, fill with props.
- Secure locations (corp offices) use tighter templates with security coverage patterns.
- Hero locations stay hand-built.

### Districts
- Hand-crafted **hero neighborhoods** per district.
- Procedural **backfill** for streets, alleyways, minor buildings outside hero zones.
- Procedural interiors attach to procgen buildings.

### Side runs
- Template combinators: **target × method × complication × twist**.
- Target: data theft, person (extraction/wetwork), artifact, sabotage, courier.
- Method: stealth, assault, social, digital, mixed.
- Complication: double-cross, rival crew, heat, moral twist.
- Assembled into a run object with fixer framing, payout, deadline.

### Loot and gear variants
- Items have a base definition (from SR rules).
- Procgen modifiers: manufacturer flavor, cosmetic variants, condition, smartlink state, source history.
- Source history is narratively interesting — a pistol might be "previously owned by a Knight Errant officer", which affects resale and risk.

### Contracts
- Similar combinator approach to side runs, but biased to short pick-up work (courier, bodyguard, legwork-for-hire).

## Hero content (not procgen)

- Main arc beats and dialogue.
- Canonical NPCs' personalities and histories.
- Signature locations (Johnson meet spots, famous bars, landmarks).
- Edition/era transition events.

## Determinism & repro

Every procgen call takes (seed, entity_id, optional context) and returns a stable output. Seeds are stored in the event log; regeneration on load is deterministic.

## Open questions

- Quality floor for procgen NPCs before they feel same-y.
- How much hand-authoring do templated side runs need before they stop feeling procedural?
- Procgen interior fidelity — cheap grid-placer vs. full layout solver.
- Procgen dialogue for minor NPCs — templates only, or small amounts of pre-generated LLM-authored variants?
