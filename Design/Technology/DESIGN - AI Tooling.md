# DESIGN - AI Tooling

## Decision

**DECIDED:** AI tools are used **at development time** to multiply a solo developer's output. They are **not used at runtime** for dialogue or content generation.

Three allowed uses:
1. **LLM-assisted authoring** of dialogue, lore, quest flavor, NPC backstories, news headlines.
2. **Generative art** for concept work and placeholder assets; painted over or used as reference, not shipped raw.
3. **Procedural generation** for districts, interiors, minor NPCs, side runs, and loot variants.

## Why no runtime LLM

- Latency and cost per player action is unacceptable for a sim game.
- Consistency / lore compliance cannot be guaranteed at runtime.
- Saves need to be deterministic; runtime LLM breaks that.
- Personal project — no infra for hosting.

## LLM-assisted authoring workflow

- Human-written seed (character sheet, scene intent, constraints).
- LLM drafts variants.
- Human edits and approves.
- Approved text enters the content database as templated lines (with variables for names, places, etc.).

All approved text is stored as data in the repo. The game never calls an LLM.

## Generative art usage

- Concept sketches to explore art direction.
- Placeholder assets during prototyping (explicitly marked).
- Backgrounds / paintings / portraits for NPCs where the style matches the painted 2.5D direction — **all retouched or repainted** before shipping.
- No raw-generated final assets. Every shipped piece is authored or retouched.

## Procedural generation

Procgen targets (see `World/DESIGN - Procgen.md` for details):

- Minor NPCs: schedules, appearances, names, contact data.
- Interiors: apartments, shops, corp offices, hideouts.
- Side runs: target + method + complication templates.
- Loot and gear variants (within SR's item taxonomy).
- District fill: non-hero streets, alleyways, back rooms.

Hero content (main arc beats, key contacts, signature locations) stays hand-authored.

## Determinism

All procgen uses seeded RNG streams keyed to stable entity IDs. Re-running the generator on the same seed produces the same output. This matters for saves, replay, and debugging.

## Open questions

- Which LLM to use for authoring (local vs. hosted)?
- Legal/ethical stance on gen-art training data — personal project, so low stakes, but decide and document.
- How templated should ambient dialogue be? One-offs vs. large combinatorial templates vs. fully procgen.
- Tooling: a small in-repo CLI for "generate 20 NPCs for district X" or ad-hoc scripts?
