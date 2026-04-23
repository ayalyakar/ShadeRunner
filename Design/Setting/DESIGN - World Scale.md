# DESIGN - World Scale

## Decision

**DECIDED:** Start with a **single deeply-simulated sprawl** (Seattle) and expand to **multiple sprawls** with travel between them over time.

## Phase plan

- **Phase 1 (MVP):** A single district of Seattle — **Redmond Barrens** — deeply built. See `Meta/DESIGN - MVP.md`.
- **Phase 2:** Remaining Seattle districts: Downtown, Bellevue, Renton, Tacoma, Auburn, Puyallup, Everett, Outremer, Snohomish, Fort Lewis.
- **Phase 3:** Secondary sprawls as major updates. Candidates (priority not fixed): Berlin (Z-Zone), Hong Kong, Denver (FRFZ), London, Tokyo.
- **Phase 4+:** Full 6th World travel (air, mag-lev, boats) and a thin simulation of distant regions as aggregate statistics.

## Travel

- Between districts within Seattle: navigable via vehicle (traffic, patrols, tolls matter).
- Between sprawls: loading screen with a travel mini-game (border crossings, SIN checks, smugglers for SINless).
- Travel has **cost and time**; SINless routes are cheaper but riskier and slower.
- Some sprawls require specific SIN tier or contacts to enter legally.

## District design

Each district has:
- **Geography** (streets, zones, canonical landmarks).
- **Faction presence** (gangs, corps, law enforcement coverage).
- **Lifestyle tier** (Squatter–Luxury distribution).
- **Economy profile** (what's easy to buy here, black-market prices).
- **Canonical NPCs** anchored here (with schedules).
- **Run flavor** — kinds of jobs typically offered from this district.

## Per-district design sheets

Each district gets a dedicated design file under `Design/Setting/Districts/` following the sourcebook-tab hybrid template (Facts, History, Downtown, Districts, Government, Economy, Crime, Maps + Hooks, MVP Notes, Open Questions). Stats are transcribed from canonical extracts and stored separately at `Data/Lore/Districts/<Name>.yaml`. See `Setting/DESIGN - Canon.md` for the ingestion policy.

Reference: `Design/Setting/Districts/DESIGN - Redmond.md` (first district implemented).

## Scale guidance

- Redmond Barrens at MVP: a hand-curated subset of streets + procedural fill. Not the full district.
- Seattle at Phase 2: each district has one or two hand-crafted "hero" neighborhoods + procedural fill.
- Sprawls beyond Seattle: similar structure, lighter coverage.

## Open questions

- How much of Seattle gets walked vs. just driven through?
- What's the in-game "fast travel" model? Any, none, taxi only?
- Procedural fill fidelity — do all alleyways need to be enterable?
- For multi-sprawl play, is there a meta-strategic layer (decade-long goals), or does the player just live somewhere?
