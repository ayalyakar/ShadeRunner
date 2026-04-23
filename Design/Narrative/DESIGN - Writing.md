# DESIGN - Writing

## Decision

**DECIDED:** Three-layer writing pipeline:

1. **Hand-written core** — main plot, arc beats, canonical NPC personalities, signature lines.
2. **Hand-written + templated procedural** — ambient dialogue, news headlines, BBS chatter, minor-NPC lines use templates filled at runtime from sim state.
3. **LLM-assisted authoring (dev-time only)** — LLMs draft variants; a human edits and approves; output is stored as static data in the repo.

**Runtime LLM generation is explicitly excluded.** See `Technology/DESIGN - AI Tooling.md`.

## Pipeline

```
  idea  →  human seed prompt  →  LLM draft  →  human edit  →  approved content (YAML/Markdown)
                                                                       │
                                                                       ▼
                                                                 runtime reads data only
```

- Nothing calls an LLM at runtime.
- Every line shipped was reviewed by a human (even if LLM-drafted first).
- Templates use variables filled from sim state, e.g. `{{contact.name}} mentioned {{last_event.rumor}}`.

## Content types

### Main plot & arc dialogue
- Hand-written, full fidelity.
- Branching, choice-tagged, reactive to player state (archetype, rep, faction standing, NSFW choices).
- Most expensive content; budget carefully.

### Side runs
- Template-driven. Run "scripts" have placeholders for target / complication / location / Johnson archetype.
- Multiple dialogue variants per Johnson archetype.
- LLM drafts variants fast; human edits ensure tone.

### Ambient content
- **News headlines.** Templated, per-event (corp merger, gang raid, Humanis rally, weather).
- **BBS / Shadowland threads.** Templated with procedurally-generated thread structure.
- **NPC idle lines.** Short barks triggered by context (time, district, weather, PC rep, NSFW flags).
- **Trid ads.** Era-appropriate, per corp and district. Includes adult / BTL ads in NSFW venues.
- **Email inbox filler.** Texture for the commlink.

### Contacts
- Each major contact has a voice guide (personality, vocabulary, tics, kinks, vices).
- Scripted scenes at trust / romance milestones.
- Procedural intermediate banter.

### NSFW scenes
- Hand-written for any named-contact / romance scene.
- Template-assisted for transactional sex work, BTL chip shoots, drug den scenes.
- LLM drafts are allowed (and expected) for variant generation, but every shipped line is human-edited. Explicit content has no filter at dev-time.
- Scene metadata: `nsfw_kind`, `intensity`, `skip_safe` (i.e. whether skipping would break narrative state).

### BBS personas
Recurring Shadowland handles are tracked as **persistent NPC personas** under `Data/Lore/NPCs/<Handle>.yaml`. Each persona carries:

- A voice profile (tone, reach, recurring opinions, vocabulary tics).
- A post history (timestamp, topic, source citation).
- Optional on-meat NPC link if the handle later maps to a physical character.

Bylined-primer format (`"Posted by: <Handle>"` on a multi-section primer) is treated as recurring from first appearance, since the byline itself signals reach.

All future content attributed to that handle — hand-authored, templated, or LLM-drafted — must respect the persona's voice profile.

## Tone management

- **No imposed game-wide tone.** Register shifts per scene: noir for wetwork briefings, pulp for neon-club chatter, romance/NSFW for intimate scenes, satire for corp-PR trid, horror for blood-magic encounters.
- Each scene has `tone_tags:` that drive LLM drafting, art style selection, music cues.
- Player choices shape overall feel; game does not moralize.

## Voice acting

- Full voice acting is **not an MVP commitment.**
- **TTS placeholder** for ambient and minor lines at MVP.
- Hero lines may eventually get human VO (post-MVP, optional).
- Voice casts can be inconsistent / swapped as long as character voice profiles stay consistent.
- All dialogue has subtitles.

## Localization

- English only.
- Localizability baked in: all shipped text in keyed resource files.
- No localization commitment.

## Open questions

- LLM choice for drafting (local vs. hosted, quality vs. control).
- Per-contact tone-tag vocabulary — how standardized?
- NSFW drafting — do we use a general-purpose LLM with a dev-time prompt, or a specialized local model for explicit content?
- How do we keep voice consistent across an LLM-drafted library that might span thousands of lines?
- Writing style guide — clear voice per POV, register per venue — lives where?
