# DESIGN - AI Tooling

## Decision

**DECIDED:** LLMs and generative AI are **dev-time collaborators, never runtime dependencies.** Everything shipped in the game is static, human-reviewed data.

## Runtime policy

**No LLM calls at runtime. Ever.**

- Game runs fully offline.
- No external service dependency.
- All dialogue, ambient, BBS, BTL content, scene text is static YAML / JSON / resource files loaded at runtime.
- This is a hard floor. If a feature is proposed that needs runtime generation, it is rejected or re-scoped to work statically.

## Dev-time in-scope

### Writing drafts
- **Use:** draft dialogue variants, BBS posts, news headlines, NPC barks, run briefs, NSFW scene text.
- **Policy:** every line a human edits and commits. LLM output is a draft, not a ship.
- **Register unlocked:** NSFW drafting included. No content filter on dev-time use for this personal project.
- **Voice consistency:** LLM is prompted with the target contact / persona voice profile (see `Narrative/DESIGN - Writing.md`).

### Image generation
- **Use:** concept art, environment mood, character portraits, NSFW illustrations, BTL chip cover art, scene illustrations.
- **Pipeline:** prompt → diffusion tool → human curation → optional hand-edit → commit to `Media/` or `Game/assets/`.
- **Ship:** static PNGs / textures. No runtime diffusion.
- **Placeholder vs. ship:** early passes use generated art as-is for placeholder; shipping scenes get human-curated or hand-edited versions.

### Code assistance
- **Use:** Claude Code / equivalent tools to write GDScript, editor tooling, data-import scripts, Godot scene setup.
- **Policy:** human reviews every diff. Code lands in git as reviewed content.

### Voice / TTS
- **Use:** placeholder voice for dialogue, ambient NPC lines, system-voice narration.
- **Pipeline:** text → TTS (local or cloud dev-time) → audio file → commit.
- **Ship:** static audio files. No runtime TTS.
- **Shipping voice:** at MVP, TTS-generated audio is acceptable as final. Post-MVP optional upgrade to human VO for hero lines.

## Dev-time tooling inventory (decided)

### LLM
- **Claude** (via Claude Code / Claude API) — primary writer / coder. Non-explicit narrative, system design, code authoring, structured data drafting.
- **Venice AI** — NSFW-capable privacy-focused LLM for explicit scene drafting (sex, extreme violence, drug-den, BTL-content scripts). Uncensored output register for this project.
- Policy: swap between the two by content register at dev-time. Claude declines to draft explicit sexual content; Venice handles those passes.

### Image generation (2D / illustrations)
- **Local: SDXL / Flux / Pony** — NSFW-capable diffusion models running locally. Primary engine for explicit scene illustrations, portrait diffusion, cover / BTL-chip art. Requires dedicated VRAM (12GB+ target).
- **Venice AI image gen** — secondary / privacy-preserving alternative when local hardware is busy. Also NSFW-friendly.
- **Style target:** cel / comic-noir 2D illustrations. See `Presentation/DESIGN - Art Direction.md` for LoRA / style-reference pipeline.

### 3D asset generation
- **Meshy** — text-to-3D and image-to-3D. Used for character model bodies, props, environment set dressing. Pipeline: generate → clean in Blender → import to Godot.
- Bespoke / hand-modeled content only where Meshy can't carry the load.

### TTS
- **Piper (local)** — lightweight local TTS for ambient NPCs, barks, placeholder dialogue. Ships at MVP as final voice for non-hero lines.
- **XTTS (local)** — higher-quality local TTS with voice cloning. Used for named / recurring contacts where voice consistency matters.
- **ElevenLabs (hosted)** — premium TTS for hero lines (PC VA if any, romance-contact key scenes, MC villain monologues). Per-use cost; reserved for scenes that warrant it.

### Coding
- **Claude Code** — primary. Human reviews every diff before commit.

## Pipeline per content type

| Content | Primary tool | Fallback | Notes |
|---|---|---|---|
| Story prose / dialogue (SFW) | Claude | — | — |
| NSFW scenes (text) | Venice AI | local uncensored LLM | Claude abstains here |
| 2D scene illustrations (SFW) | Local SDXL/Flux/Pony | Venice image | Style LoRA for cel/comic-noir |
| 2D NSFW illustrations | Local SDXL/Flux/Pony | Venice image | Local preferred for policy freedom |
| Character portraits | Local SDXL | Venice image | Per-chargen at PC creation |
| 3D character models | Meshy | Blender hand-model | Rigged in Blender after gen |
| 3D props / environment | Meshy | hand-model / CC0 kits | — |
| Audio ambient / barks | Piper | — | Ship as MVP voice |
| Audio named contacts | XTTS | Piper | Voice cloning for consistency |
| Audio hero lines | ElevenLabs | XTTS | Budget per-scene |
| Code | Claude Code | — | Human review required |

## Storage & citation

- **Generated assets** (text, images, audio) shipped in the repo are no different from hand-authored assets — they are committed, version-controlled, and referenced by `Data/` or scene files.
- **Optional provenance metadata:** a `generated:` field on data records can note source model / prompt / date for later re-generation or review.

## Hard-floor content policy (dev-time)

- **No sexual content involving minors** in any generation — prompt, draft, or ship. This is an absolute, model-independent limit.
- All other SR dark content is in scope per `Meta/DESIGN - NSFW.md`.

## Why no runtime LLM?

- **Determinism.** Saved games and replay should produce stable content.
- **Offline.** The game runs without an internet connection.
- **Latency.** Runtime generation introduces response-time unpredictability in dialogue.
- **Cost.** No per-play API bill.
- **Safety.** All content is reviewed before shipping; no surprise outputs.
- **Archival.** Static content means the game still works in 10 years when the current LLM endpoints are gone.

## Open questions

- Which specific SDXL / Flux / Pony checkpoint to pin as the project's default? (Style consistency requires pinning.)
- Style LoRA training for cel / comic-noir — train a project-specific LoRA on curated references, or rely on prompt + base checkpoint?
- Meshy output quality threshold — how much Blender cleanup per generated model?
- Venice AI reliability for long-form drafting — does it handle full-scene scripts, or just snippets?
- Prompt library organization — `Media/Prompts/<Content-Type>/<slug>.md` or prompts live with the output they produced?
- Regeneration consistency — character seed / reference image / negative prompt discipline to keep PC and NPC looks stable across re-draws.
- ElevenLabs cost budgeting per scene — per-session hero-line cap?
- Meshy → Godot rig pipeline — manual rigging in Blender each time, or auto-rig?
