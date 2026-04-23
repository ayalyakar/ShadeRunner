# DESIGN - Modding

## Decision

**DECIDED:** **Closed, personal-use only** for now. Reconsider later.

## Current stance

- No official modding API.
- No plans to publish source.
- Game data files (JSON / YAML) exist in a form that could later be exposed, but aren't documented as a modding surface.
- No plugin loader.

## Why

- Solo developer; modding support adds complexity and expectation.
- Personal project — no community to serve.
- Stability and iteration speed benefit from not locking an API.

## Data-driven architecture (benefit retained without modding)

Even without modding, core design is data-driven:
- Gear, spells, programs, NPCs, traits, qualities all defined in resource files.
- Easy to rebalance and iterate.
- Future modding (if opened) would build on this substrate.

## Later options (if reconsidered)

- **Full data-driven modding** — expose resource files, allow overrides and additions.
- **Godot scripting API** — expose selected signals / hooks to modders.
- **Open source** — publish under permissive license.

None are committed; none are ruled out forever.

## Open questions

- Would publishing to a small audience someday benefit from modding?
- Is there any risk to a "maybe later" stance for API stability? (Probably not; data-driven fences keep options open.)
