# DESIGN - Art Direction

## Decision

**DECIDED:** **Stylized HQ painted 2.5D**, blending:

- **2D illustrated / comic-noir** for cutscenes, portraits, hero panels.
- **Mid-fidelity stylized 3D** for in-world play (isometric and first-person).
- Shared palette and line / lighting language across the two registers so they read as one game.

No photorealistic 3D. No raw AI-generated assets in the final product.

## Aesthetic pillars

- **Painted, not photographed.** Texture work emphasizes brushstroke and ink, not PBR.
- **Cyberpunk with rainbow neon and wet streets** — but authored, not generic.
- **Era-dependent style shifts** — SR1–3 chunky chrome & CRT glow; SR4–5 sleek, seamless; SR6 biopanel organic.
- **Readability over spectacle.** The player must parse an isometric scene at a glance.
- **Cohesive at any resolution** — art scales down gracefully; target is strong silhouettes and palette.

## 2D panels

- Hand-painted comic-style compositions.
- Used for: cutscenes, flashbacks, Astral visions, dream sequences, character portraits, key narrative beats.
- Panel templates exist for efficiency; hero moments are fully bespoke.
- Inked line + painted color + limited palette.

## 3D in-world

- Stylized characters and environments.
- Clear silhouettes, painterly textures, baked lighting where feasible.
- Modest poly counts; invest in silhouettes and shading over geometry detail.
- Custom shaders for painted / toon look; consistent across isometric and first-person views.

## Palette

- Per-district palettes — Redmond Barrens is rust and acid, Downtown is chrome and cyan.
- Magic visuals get their own color language (Astral auras, spirit effects, Awakened signatures).
- Matrix deep-dive uses a distinct palette (high contrast, grid-first, era-variable).

## Asset pipeline

- Generative AI used for concept art and placeholder assets; **nothing raw-generated ships**.
- Painted-over gen output is acceptable only when it reaches the consistency bar.
- Procedural interiors use an asset palette (props, lights, floor kits) rather than generated geometry.
- Asset budget per district: kit of ~N props / kitbash reusable; hero props are bespoke.

## Characters

- Portraits hand-painted per major NPC.
- Body types, metatypes, cyberware visible.
- Clothing system supports layering and era / subculture expression.
- Painted portraits for contacts; procedural / kit characters for crowd.

## VFX

- Painted style persists into effects: spells look painted; gunfire has ink-splash; cyberware glow is hand-tuned.
- No over-reliance on post-processing.

## Open questions

- 3D-to-2D render pipeline — render painted-looking frames from 3D, or keep hand-painted distinct from 3D?
- Number of palette variants per district.
- How do dynamic era transitions look — does Redmond visibly age across decades?
- Target resolution / aspect ratios.
