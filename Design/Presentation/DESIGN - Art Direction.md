# DESIGN - Art Direction

## Decision

**DECIDED:** Two art layers running in parallel:

1. **3D isometric world** — rendered in Godot 4. Characters, props, and environments are 3D models (Meshy-generated, cleaned in Blender, shaded stylized). Camera locked isometric.
2. **2D scene illustrations** — cel / comic-noir style. Used for dialogue portraits, chargen preview, dream / BTL / flashback sequences, romance and explicit scenes, key cinematic beats.

The 3D layer is the default playing surface. The 2D illustrations interrupt when story / NSFW / cinematic beats call for them.

## Visual identity

### Core style pillars
- **Noir cyberpunk.** Rain, neon, wet pavement. Saturated accents against muted base palette.
- **Period-authentic 2050 tech.** Bulky cyberdecks, CRT monitors, clunky commlinks. Not sleek Cyberpunk-2077 chrome.
- **Metahuman-visible world.** Trolls are massive; Orks are distinct; Elves are inhuman-beautiful. Metatype reads at a glance in both 3D and 2D.
- **Tonal range.** The game drifts from gritty noir to pulpy neon to intimate-romance to horror. Art adapts per scene tag.

### Palette
- **Base:** desaturated greys, browns, deep blues (Redmond Barrens decay).
- **Accents:** hot neon (magenta, cyan, electric green) for signage, corp branding, magic, cyberware glow.
- **Blood / violence:** deep red; not comic-book bright.
- **Magic:** color-coded by tradition (Hermetic = cool blue / violet; Shamanic = earth-tone greens / browns; blood magic = rust / black).

## 3D layer

### Characters
- **Pipeline:** Meshy (text-to-3D or image-to-3D) → Blender cleanup / rigging → Godot import (glTF).
- **Rigs:** per-metatype base rig (Human / Elf / Dwarf / Ork / Troll). Character meshes retargeted.
- **Animations:** starter library — walk, run, idle, combat-ready, shoot, cast, hit-reaction, death, sit, drink. Animation library lives in `Game/assets/animations/`.
- **Faces:** low-detail in 3D; character identity read through portrait illustrations (2D layer).
- **Fidelity target:** stylized, readable at iso zoom; no hair / fabric simulation at MVP.

### Props & environment
- **Tileset-based** where possible (modular buildings, alleys, rooms).
- **Hero props** hand-modeled or Meshy-refined for key story objects (Johnson's artifact for the MVP retrieval, romance-contact's apartment details).
- **Environment art** at MVP: one Redmond neighborhood tile set, ~6–10 interior sets (fixer bar, PC apartment, Johnson meet room, romance-contact apartment, execute-run target interior, street doc clinic, brothel/BTL venue).

### Lighting & shading
- **Stylized cel-shading** shader on characters (sharp lighting bands, rim light).
- **Environment lighting:** dynamic day/night, rain overlays, neon emissive surfaces.
- **Mood-per-scene:** scene-specific LUT / post-process profile (e.g. dream-BTL = heavy chromatic aberration + bloom).

## 2D layer

### Scene illustrations
- **Style:** cel / comic-noir — strong ink lines, flat-ish color fills, painted shadows. Think Sin City meets cyberpunk graphic novel, with explicit-scene register for NSFW.
- **Pipeline:** local SDXL / Flux / Pony (NSFW-capable) → human-curated selection → optional Photoshop / Krita touch-up → commit.
- **Style LoRA:** train a project-specific LoRA on curated references once a corpus exists (post-first-scene).
- **Character consistency:** reference images + character seed + textual-inversion embeddings per named character for cross-scene consistency.

### Portrait pipeline
- **Chargen PC portrait:** diffusion-generated per chargen choices (metatype, archetype hint, appearance seed). Locked to save-game; regeneratable on player request.
- **Named NPC portraits:** diffusion-drafted, human-curated, committed. Stable across the campaign.
- **Emotive variants:** per named NPC, a small set (neutral / angry / flirting / hurt / amused) for dialogue UI reactivity.

### NSFW illustrations
- **Primary tool:** local SDXL / Flux / Pony (NSFW unlocked).
- **Style:** same cel / comic-noir register as SFW scenes — consistency across the game.
- **Animation:** static stills at MVP. **Animated sex scenes as a stated post-MVP goal.**
- **Authorial control:** project-lead curates; no auto-shipping of generated content.

## Scene type matrix

| Scene type | Layer | Tools | MVP coverage |
|---|---|---|---|
| World exploration | 3D | Godot render + Meshy models | MVP |
| Tactical combat | 3D | Godot render + animation lib | MVP |
| Dialogue | 3D (optional) + 2D portraits | Godot + SDXL portraits | MVP |
| Chargen | 2D | SDXL portraits + UI | MVP |
| Story beats / cinematics | 2D illustration | SDXL cel-noir | MVP |
| NSFW scenes | 2D illustration | Local SDXL unrestricted | MVP (static) |
| Matrix | Stylized 2D UI | Godot UI + diffusion backgrounds | MVP |
| Animated sex | 2D animated | Post-MVP | Post-MVP |

## Consistency toolkit

- **Character seed registry:** `Media/Characters/<name>/seed.yaml` with prompt / seed / reference images / pose refs.
- **Style references:** `Media/StyleRefs/cel-noir/` — curated image library for LoRA training and prompt references.
- **Negative prompt library:** `Media/Prompts/negative.md` — shared across generations to avoid common diffusion failures.

## Naming / storage

- **Raw / pre-ship art:** `Media/Concepts/`, `Media/Raw/`.
- **Shipping assets:** `Game/assets/art/<category>/<slug>.png` (2D), `Game/assets/models/<category>/<slug>.glb` (3D).
- **Prompts alongside outputs:** each generated asset directory has a `prompt.md` recording model, checkpoint, prompt, seed, date.

## Open questions

- SDXL vs. Flux vs. Pony checkpoint pin for the project? (Pick one primary; keep alternates for specific scene registers.)
- LoRA training timing — do we train before or after first shipped scene?
- 3D face detail ceiling — readable at iso, but do we need close-up shots ever?
- Per-scene LUT / post-process library — author one pipeline or per-scene hand-tuning?
- Rain / weather rendering cost — MVP target or post-MVP?
- Meshy model quality threshold — how much Blender cleanup minimum per shipped model?
- Animation library size — hand-authored / mocap / auto-rig? Solo animator budget is tight.
- Cinematic camera for 3D scenes — locked iso always, or camera-unlock for specific cutscenes?
