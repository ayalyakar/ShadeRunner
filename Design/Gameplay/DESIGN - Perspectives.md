# DESIGN - Perspectives

## Decision

**DECIDED:** The game is **context-switching**: different perspectives engage depending on what's happening. Five views, all first-class:

1. **Isometric / top-down tactical** — active for runs, combat, group encounters.
2. **First-person immersive** — active for exploration, stealth, dialogue, sensory moments.
3. **Terminal / text interface** — for BBS, deep Matrix, shadowland shells, diegetic computing.
4. **2D painted cutscenes / comic panels** — for narrative beats, flashbacks, dream sequences, hard-boiled story moments.
5. **Matrix deep-dive 3D/VR** — separate rendered cyberspace layer for decker protocols (see `Systems/DESIGN - Matrix.md`).

## Transition philosophy

- Transitions are **diegetic** where possible — entering a building, jacking into a terminal, slotting into a drone — not abstract mode toggles.
- Each view has consistent controls within itself. Views never fight each other.
- The player can anticipate which view applies before committing (no surprise mode switches mid-action).

## Per-view specifics

### Isometric tactical
- Default for combat, break-ins, shootouts, heists.
- Grid-less, phase/pass SR initiative on a timeline (see `Systems/DESIGN - Combat.md`).
- Top-down camera with tilt.

### First-person immersive
- Default for exploration, dialogue, stealth.
- Sensory: footsteps, voices, AR overlays.
- Supports crouching, leaning, interacting with objects.

### Terminal / text
- BBS (including Shadowland), corporate mail sifting, low-level decking.
- Text-first UI with diegetic "your commlink" framing.
- Usable from anywhere the PC has commlink access.

### 2D painted panels
- Cinematics, key story beats, flashbacks, Astral visions.
- Hand-crafted panels for hero moments; templated compositions for less critical beats.

### Matrix deep-dive
- Only when a decker fully jacks in.
- Separate 3D environment (cyberspace) with icons, hosts, IC.
- Time-dilated relative to meat world.

## Per-context mapping (initial)

| Context | Primary view |
|---|---|
| Walking the streets | First-person |
| Driving | First-person (or isometric if in a vehicle mission) |
| Combat | Isometric tactical |
| Stealth infiltration | First-person |
| Matrix dive | Terminal + deep-dive 3D |
| Astral projection | First-person (AR-tinted) |
| Cutscene | 2D painted |
| Johnson meet | First-person (in venue) |

## Open questions

- Can the player lock a preferred view (e.g. always isometric)?
- How to handle the Astral overlay cleanly when it coexists with meat space.
- Camera during drone jump-in: first-person from drone, with drone's sensors.
- 2D-panel quality bar vs. production cost.
