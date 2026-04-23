# DESIGN - Audio

## Decision

**DECIDED:** Full audio ambitions on three fronts:

1. **Full voice acting** — all dialogue voiced (long-term goal; placeholder TTS acceptable en route).
2. **Dynamic adaptive music layers** — stems that shift with district, tension, faction, time-of-day.
3. **Original / synthwave-cyberpunk score** — composed soundtrack with strong SR identity.

Diegetic-only / no-score minimalism is **not** chosen.

## Voice acting

- Hero content (main plot, arcs) targeted for full VO.
- Minor NPCs: may rely on brief barks only, or TTS at lower quality.
- Placeholder AI TTS during development; human VO for shipping where feasible.
- Consistency per character: the same voice actor per NPC if possible; otherwise a voice profile doc documents the intended delivery.
- Subtitles always on by default; never relied-upon exclusively for accessibility.

## Dynamic adaptive music

- Layered stems: **base**, **rhythm**, **lead**, **risers/stingers**.
- Layers fade in/out based on gameplay state:
  - Ambient exploration (one stem).
  - Suspicion raised (add rhythm).
  - Combat (add lead + stingers).
  - Astral / Matrix transitions (palette swap).
- Per-district palettes — Redmond has dirtier, rougher palette; Downtown has sleek corp sound.
- Era variations — SR1 synth, SR4 wireless-era, SR6 current.
- Per-faction themes for canonical encounters.

## Score direction

- Synthwave as backbone, with 6th-World flavor: low-fi analog hum, ritual percussion, AR-jingle textures.
- Authored pieces for key locations, characters, and arcs.
- Reuse via leitmotifs for canonical NPCs.
- License-vs-original: all original; no licensed music.

## SFX

- Full foley: footsteps by surface, weapon reports, cyberware hum, mag-lev rumble.
- Magic SFX per tradition (hermetic crystalline, shamanic drum/natural, etc.).
- Matrix SFX: modem-era shrieks in SR1-3, ambient wireless hum in SR5-6.
- Vehicle audio: engine models by era; corp cars sound different from gang beaters.

## Diegetic audio

- In-world trid, radio, BBS chatter audible in venues.
- Commlink notifications have a per-PC ringtone set.
- Environmental soundscape drives immersion (rain, crowd murmur, sirens, dragons in the distance).

## Mixing

- Spatialized 3D audio for first-person.
- Flat-mix stereo presentation for isometric with proximity cues.
- Dynamic range manageable — shadow runs shouldn't blow out speakers.

## Open questions

- TTS quality bar for ambient lines — acceptable forever, or replaced eventually?
- Licensed tracks for diegetic radio (could add mood) — but personal project, so original originals.
- Music system architecture: FMOD / Wwise / custom in Godot?
- Voice pipeline: auditioning vs. commissioning vs. crowd-sourcing.
