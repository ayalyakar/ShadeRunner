# DESIGN - Engine

## Decision

**DECIDED:** **Godot 4**, **GDScript** primary language, **Windows** target, **3D isometric** renderer with fixed camera.

## Engine: Godot 4

- **Open-source.** No licensing risk, no royalty, no engine-company pricing drama.
- **Cross-platform friendly.** Windows is the target; Linux / Mac come for free if ever needed.
- **Solid 3D isometric workflow.** Native orthographic camera, 3D physics, navmesh, lighting, shaders.
- **Lightweight editor.** Iteration is fast; launches in seconds.
- **GDScript has Python-like ergonomics.** Cheap gameplay scripting.
- **Data-driven friendly.** Easy YAML/JSON import via native file APIs.

Versioning: pin to a specific Godot 4.x minor release for the project's lifetime; upgrade only deliberately, with a migration pass.

## Language: GDScript (primary)

- Native to Godot. Fastest iteration for gameplay code.
- Python-ish syntax; minimal ceremony.
- Performance ceiling is an acceptable tradeoff for MVP; if a system hits that ceiling, we can drop to C# or GDExtension (Rust / C++) for that subsystem only.

### Escape hatches
- **C#** — acceptable for performance-critical or type-strict systems if GDScript hits limits.
- **GDExtension (Rust / C++)** — simulation hot paths, pathfinding, large-scale AI if needed. Not MVP.

## Renderer: 3D isometric

- 3D-rendered assets (characters, props, environments).
- **Orthographic camera, fixed angle** (classic CRPG iso).
- Camera zoom allowed; rotation snap (e.g. 90° increments) to be decided.
- Lighting: dynamic, supports time-of-day cycle.
- Shaders: stylized shading preferred (cel / flat / noir) over photo-real — cheaper art budget, distinctive look.

### Why 3D over 2D sprites
- Animation reuse (one rigged skeleton, many NPCs).
- Variable-angle flexibility even under fixed camera (camera-rotate in special scenes).
- Modernizes the SR visual register without requiring photoreal AAA art.
- Works with diffusion-tool art for textures / concept art / illustrations; 3D skeletons drive gameplay, 2D art drives portrait / scene illustrations.

## Target platform

- **Primary:** Windows.
- **Linux:** not a commitment, but will likely work given Godot.
- **Mac / web / console:** out of scope.

## Performance targets

- 60 FPS at reasonable resolutions on mid-tier Windows hardware.
- Memory: not fixed; personal target is "runs on the dev machine comfortably."
- Load times: under 3 seconds between scenes at MVP.

## Input

- **Mouse + keyboard** primary.
- Controller support: not an MVP commitment.
- Rebindable keys.

## Save system

- **Save-anywhere.** Serialized world state to disk.
- Save slots; no ironman.
- Save format: JSON or Godot's native resource serialization — TBD in `DESIGN - Persistence.md`.

## Modding

- **Not an MVP commitment.** Design data-driven where cheap, so modding is possible later if appetite exists. No mod loader, no scripting API shipped at MVP.

## Architecture (pending)

Detailed architecture doc deferred — scene structure, autoloads, event bus, save-state separation, simulation tick model to be decided in a dedicated `DESIGN - Architecture.md` once first gameplay systems are being built.

## Open questions

- Godot 4.x minor version pin.
- Camera rotation — fully locked, 4-facing snap, or freely rotatable?
- Character model pipeline — Blender + glTF, or Mixamo-adjacent, or diffusion-assisted?
- Navmesh granularity for indoor (cover-heavy) scenes.
- TTS engine for placeholder voice (native, local model, or cloud)?
- Physics: Godot 3D physics or deterministic custom tick for combat (reproducibility for tactical)?
