# DESIGN - Audio

## Decision

**DECIDED:** Three-tier voice pipeline — **Piper** (local) for ambient / minor lines, **XTTS** (local, voice-clone-capable) for named / recurring contacts, **ElevenLabs** (hosted) for hero lines at premium scenes. Music and SFX hand-assembled at MVP; no runtime audio generation.

## Voice

### Tier 1: Piper (local)
- **Use:** ambient NPC barks, crowd chatter, minor-NPC shop lines, placeholder dialogue during early development.
- **Why:** free, local, fast, unlimited. Quality acceptable for non-hero lines.
- **Voices:** a small curated set of Piper voices mapped to metatype + age + tone (e.g. "Ork male gruff", "Elf female neutral", "Human female cheerful").
- **Shipping:** MVP ships Piper audio as final voice for all ambient / crowd lines.

### Tier 2: XTTS (local)
- **Use:** named recurring contacts, fixer, Johnson, romance contact, street doc, major faction NPCs.
- **Why:** higher quality than Piper, supports voice cloning from short reference audio — gives each named NPC a consistent, distinct voice for the life of the campaign.
- **Pipeline:** collect 30–60 seconds of reference audio per NPC (from curated voice library — actor clips, AI-generated seed, public-domain recordings); train / configure XTTS voice per NPC; generate all that NPC's lines from the same voice profile.
- **Shipping:** MVP ships XTTS audio as final for named NPCs.

### Tier 3: ElevenLabs (hosted)
- **Use:** hero lines — MC villain monologues, key romance-scene reactive lines, PC-reactive lines in cinematic beats. Budgeted per scene.
- **Why:** best emotional range; most expressive delivery. Per-use cost; hosted-service NSFW policy may apply — reserved for SFW / suggestive content. Explicit NSFW dialogue stays local (XTTS).
- **Shipping:** specific scenes only; not per-NPC. Falls back to XTTS for same NPC's non-hero lines.

### Voice assignment
Each named NPC has `voice:` declared in `Data/Lore/NPCs/<name>.yaml`:

```yaml
voice:
  engine: xtts
  model_ref: "voices/fixer-seasoned-redmond.safetensors"
  reference_audio: "Media/Audio/Voices/fixer-seasoned-redmond.wav"
  pitch: 0
  energy: 0.8
  hero_engine: elevenlabs       # optional; used when scene tag = hero
  hero_voice: "Rachel"
```

### Dialogue subtitle policy
- Every dialogue line has a subtitle. Always on.
- Subtitle is the text file source of truth; audio is generated from that text.

## SFX

### Pipeline
- **Libraries:** curated commercial SFX libraries (licensed or CC0) as the base.
- **Hand-edits:** Audacity / Reaper edits for scene-specific cues.
- **Tagging:** per-sample metadata for context (combat / ambient / UI / magic / Matrix / vehicle / crowd).
- **No runtime AI generation.** Committed WAV/OGG files only.

### Coverage at MVP
- **Combat:** weapon fires, melee impacts, wound / death cries, armor hits, reload, footsteps (per metatype mass).
- **Magic:** per-spell cast, spirit materialize, drain hit, astral transition.
- **Matrix:** persona-in / jack-out, IC encounter stingers, utility cast.
- **Ambient:** rain, traffic, distant gunfire, distant crowd murmur (per-neighborhood).
- **UI:** hover / select / confirm / cancel / equip.
- **NSFW audio:** ambient scene audio (soft vocalization, rustle) for illustrated explicit scenes. MVP target is suggestive-not-graphic on audio, with art carrying explicit weight.

## Music

### Composition approach
- **Primary option: curated licensed / CC0 library** for MVP. Avoid custom composition cost until post-MVP.
- **Alternate option:** AI-generated music (Suno, Udio, MusicGen local) committed as static files — same policy as voice (no runtime generation).
- **Scoring depth:** scene-triggered cues at MVP; no dynamic adaptive music layer (post-MVP if ever).

### Style
- **Primary register:** synth-noir, industrial, dark ambient. Cyberpunk-noir mood.
- **Secondary registers:** pulpy neon / retrowave (upbeat beats), magical / tribal (Shamanic scenes), romantic / melancholic (romance scenes), horror / drone (blood magic / Matrix Black IC / body horror).
- **Per-venue themes:** fixer bar has its own track, brothel / BTL studio has its own, etc.

## Mixing

- Scene-type audio profiles (Master / Music / Dialogue / SFX / Ambient) with scene-specific attenuation (dialogue ducks music, combat boosts SFX).
- Radio / trid diegetic audio routed through in-world speakers (attenuates with distance / occlusion).
- 3D spatial audio for SFX in combat / exploration scenes.

## Accessibility

- Full subtitle / transcript for all dialogue, mandatory.
- UI sound cues paired with visual cues (no audio-only signals).
- Option to disable ambient / music independently of dialogue.

## MVP deliverables

- Piper voice library: 6–10 preset voices across metatypes.
- XTTS voice library: ~8 named NPC voices (fixer, Johnson, PC VA placeholder, romance contact, street doc, ganger archetype, Lone Star archetype, romance-contact romantic-scene voice pass).
- ElevenLabs: 2–3 hero-scene lines authored.
- SFX library covering combat / Matrix / magic / UI / ambient baseline.
- Music: 6–10 tracks covering Redmond-noir / combat / bar / brothel-BTL / romance / Matrix registers.

## Open questions

- Piper voice set — which ones pass the gritty-SR sniff test?
- XTTS reference-audio sourcing (ethical considerations; use synthetic seeds if in doubt).
- ElevenLabs NSFW policy fallback — ensure romance scenes don't accidentally route there for explicit dialogue.
- Music licensing terms for curated library — verify commercial-equivalent terms even for personal project.
- Adaptive music at combat state changes — MVP or post-MVP?
- Accessibility: colorblind indicators? Deaf support beyond subtitles?
- Voice barking volume: when does a random NPC speak vs. stay silent?
