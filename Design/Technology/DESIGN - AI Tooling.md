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

## Dev-time tooling inventory (evolving)

- **LLM for writing:** Claude (via Claude Code or the Claude API); local model as a fallback for any content that cannot be drafted via hosted services. TBD which local model handles explicit NSFW drafting.
- **LLM for code:** Claude Code.
- **Diffusion for art:** TBD (Stable Diffusion XL / Flux / similar, local). Model choice influenced by NSFW register (needs a model comfortable with explicit content).
- **TTS:** TBD (local: Piper, XTTS; hosted alternatives).

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

- Local vs. hosted LLM for NSFW drafting — tradeoffs for explicit register vs. hosted-service policy.
- Diffusion model choice — image quality vs. content-policy freedom vs. VRAM needs.
- Tooling for batch-generating NPC portraits for procgen crowds.
- Standardized prompt library — where do prompts live? Committed alongside outputs?
- Consistency across regenerations — how do we keep voice / character look stable when re-drafting later?
