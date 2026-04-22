# DESIGN - Engine

## Decision

**DECIDED:** Godot 4 as the base engine, extended with custom modules (GDExtension / C++ / Rust) for performance-critical subsystems.

## Rationale

- Solo-friendly: GDScript iteration speed is critical for one-person development.
- Open source, no runtime royalties, no legal constraints for a personal project.
- Integrated 2D + 3D pipeline matches the planned stylized painted 2.5D art direction (see `Presentation/DESIGN - Art Direction.md`).
- 4.x has matured enough for non-trivial games; weaknesses (large-scene perf, networking) are not blockers here.

## Extension points (custom modules)

Custom modules are added **only when GDScript hits a wall**, not pre-emptively. Known candidate areas:

1. **World simulation tick.** Thousands of NPC agents with schedules, goals, memory — likely needs C++/Rust via GDExtension.
2. **Combat resolver.** Phase-pass initiative, dice pools, probability trees — a fast native implementation will matter during large encounters.
3. **Matrix layer.** Graph traversal, IC pathing, program interaction — could be a small DSL or a native subsystem.
4. **Pathfinding at sprawl scale.** Hierarchical navmesh over a whole city.
5. **Save / event-log (de)serialization.** Per-NPC action logs can get huge; native (de)serialization avoids GDScript overhead.

## Language policy

- **GDScript** for UI, scene glue, scripted events, quick iteration.
- **C#** only if a well-maintained library demands it (currently none planned).
- **C++ via GDExtension** for performance hotspots.
- **Rust via GDExtension (godot-rust)** is the preferred systems language if a hotspot needs a real implementation — better safety, better concurrency story than C++.

## Build / tooling

- Linux + Windows export targets from day one. Both tested regularly.
- Version control: Git, LFS for art/audio.
- Reproducible builds via a Makefile / just recipes.

## Open questions

- Godot's threading story vs. a separate simulation process — decide once sim prototype exists.
- godot-rust vs raw C++ — Rust preferred, needs a small spike to confirm ergonomics.
- Physics: Godot's Jolt integration or built-in? (Likely Jolt for better 3D behavior.)
