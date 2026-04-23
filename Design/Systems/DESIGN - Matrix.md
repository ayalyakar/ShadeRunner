# DESIGN - Matrix

## Decision

**DECIDED:** Matrix is an **abstract minigame** with its own dedicated scene / UI. Canon flavor: **SR1E wired Matrix baseline** at era-start (2050), with **post-Crash wireless drift** eligible post-MVP when era transitions are simulated. The Decker is a first-class MVP archetype.

## Canon baseline — SR1E wired Matrix

- **Physical jack-in:** decker's cyberdeck connects to the Matrix via a datajack (cyberware) and a physical jackpoint (wired wall port, tap into a trunk line, hook into a device).
- **Deck carried:** like a laptop; weight and concealability matter.
- **Host topology:** Matrix hosts are discrete nodes with input/output ports, subsystems, and IC (Intrusion Countermeasures) defending them.
- **Subsystems per host** (classic SR1E): **Access · Control · Files · Slave · Index**. Each has a rating; decker attacks subsystems with utilities (Deception, Read/Write, Graceful Logoff, Analyze, etc.).
- **IC types:** White / Gray / Black — escalating lethality. Black IC can kill the decker (brain-burn / cardiac arrest via dumpshock-chained biofeedback).

## UI & scene surface

- **Separate Matrix scene.** Not a 3D cyberspace environment — abstract node-graph UI with iconography.
- **Nodes as rooms:** the decker "moves" between nodes on a graph; each node shows its subsystems, IC presence, and available utility actions.
- **Timing:** a Matrix action consumes a Pass (phase-pass model from `DESIGN - Combat.md`). Meat time advances in parallel.

```
Matrix scene layout (concept):
  ┌─────────────────────────────────────────────────┐
  │  Host: Aztechnology R&D Subnet                  │
  │  Current node: [ Index ] → [ Files ]            │
  │                                                 │
  │   ┌── Index ──┐                                 │
  │   │ rating 6  │                                 │
  │   └───────────┘                                 │
  │        │                                        │
  │   ┌── Files ─────── Slave ──┐                  │
  │   │ rating 8 ── Control ─── │                  │
  │   └── Access ───────────────┘                  │
  │                                                 │
  │  IC presence: 1 White Sleaze, 1 Gray Trace     │
  │  Cyberdeck: MPCP 5 · Hardening 3 · Memory OK   │
  │  Persona: 8 dice · Masking on                   │
  │                                                 │
  │  Actions:  [Deception] [Analyze] [Graceful LG]  │
  │            [Read File] [Crash IC] [Jack Out]    │
  └─────────────────────────────────────────────────┘
```

## Decker stack at chargen

A Decker's starting kit at chargen (MVP):

- **Datajack** (cyberware, 0.2 Essence, 1,000¥).
- **Cyberdeck** (gear, varies by MPCP rating and options).
- **Utility library:** starter set of utilities at various ratings (Deception, Read/Write, Analyze, Decrypt, Sleaze, Attack, Armor, Shield).
- Skills: **Computer** (programming / host navigation), **Electronics** (deck repair / hardware), optional **Biotech** (first aid for dumpshock).

## Cyberdeck stats

A cyberdeck has:
- **MPCP (Master Persona Control Program):** the deck's core rating — caps persona attribute ratings.
- **Hardening:** reduces damage to the persona from IC attacks.
- **Active / Storage Memory:** capacity for utility loads and file storage.
- **I/O Speed:** how fast the deck uploads / downloads.
- **Bod / Masking / Sensor / Evasion:** persona attributes deriveed from MPCP with upgrades.

## Persona

Decker enters the Matrix as a **persona** — a digital projection with its own dice-pool attributes:
- **Bod:** resist IC damage.
- **Masking:** stealth in the Matrix (oppose Trace / Detect).
- **Sensor:** perceive the Matrix, identify IC, analyze hosts.
- **Evasion:** dodge attacks.

Persona attributes are capped by the deck's MPCP rating.

## Core loop (MVP)

A Matrix run in MVP covers one decking sequence:

1. **Jack in.** Locate a jackpoint physically (adjacent wall port, tap a cable, hook into a target device). Pass action: connect.
2. **Navigate** to the target host (skip if already in). Open connections: Access subsystem; utility: **Deception** vs. Access rating. Detected → raises alert.
3. **Locate target data** (Files subsystem) or **target node** (Slave / Control for device).
4. **Extract / control:** Read file, Download file, Change slave device state (open door, disable alarm, dump cameras).
5. **IC encounters** as alert rises: White IC first, escalating.
6. **Graceful Logoff** to avoid dumpshock, or emergency **Jack Out** (risks dumpshock Stun damage; risks Black IC lethal feedback).

## Alert level

- **Green → Yellow → Red → Black.**
- Each failed test (Detection success against decker) raises alert.
- Alert escalation spawns more IC, upgrades IC ratings, alerts physical security (door-locks, cameras on alert — ties into meat scene).

## Meat-vs-Matrix interleave (MVP implementation)

- Decker's **meat body is vulnerable while jacked in.** A guard can walk up and shoot the unconscious-looking decker.
- **Defend the meat body:** party members (in MVP: the scene's NPC allies) can guard the decker's physical body. Post-MVP: companion control.
- **Jacking out:** free action if uninterrupted; contested (dumpshock risk) if forced.
- **Dumpshock:** forced disconnect → Stun damage proportional to IC-induced feedback. Black IC forced disconnect can be Physical damage.

## Matrix skills & utilities

### Skills
- **Computer** — dice-pool for most actions (Deception, Analyze, Read/Write, Control).
- **Electronics** — hardware side (deck repair, jackpoint physical access).
- **Decking** (sub-skill under Computer, or merged depending on skill tree finalization) — general Matrix operations.

### Utilities (programs)
- **Deception:** sleaze past Access without tripping IC detection.
- **Analyze:** identify host topology, IC type, subsystem ratings.
- **Read/Write:** manipulate files.
- **Attack:** crash IC (the "combat" inside the Matrix).
- **Armor:** defensive program; resists IC attacks.
- **Shield:** defends against dumpshock feedback.
- **Sleaze:** masks persona from casual detection.
- **Smoke:** escape utility — blind IC briefly to disengage.

Each utility has a **rating** (how strong it is — higher rating = more dice or better TN).

## Matrix in runs (MVP)

The MVP run's Legwork or Execute phase includes **at least one** Matrix sequence. Sample integration:

- **Legwork:** Decker jacks into a sub-host to pull target layout, guard rotations, security codes. Success gives +2 dice to Execute stealth, or reveals an alternate entry.
- **Execute:** During physical infiltration, Decker hacks cameras and door-locks in real time, while the street sam sneaks past.
- **Alternate run path:** a run can be resolved entirely from the Matrix (data heist) — decker pulls the file, meat team exists only as extraction backup.

## Post-MVP

- **Wireless Matrix** (post-Crash-2.0 canonical era drift).
- **Full IC bestiary** (Killer, Blaster, Sparky, Tar Baby, Scramble, Black IC variants).
- **Host topology deeper** (subsystem interactions, chained hosts, UMSs).
- **AI / dissonance resonance** (Resonance-style technomancers) — deferred or may stay out of scope.
- **Custom utility coding** (Decker can author their own utilities in downtime for karma + nuyen).
- **Corporate host variety** — differentiate Fuchi, Aztechnology, Renraku, Mitsuhama, etc. by topology style.

## Open questions

- UI style — pure 2D node graph, stylized "cyberspace corridors," or animated icon-shifting?
- Does the player see exploded dice in the Matrix scene, or only outcome ticks?
- How granular is the physical-jackpoint requirement in MVP? (Every jack-in requires adjacency to a physical port?)
- Time compression — does Matrix time advance at meat-time 1:1 during interleave, or slower?
- Non-decker character Matrix use — a sam with a commlink can make skill checks to use public Matrix features; what's their UX?
- Matrix-only tutorial run feasibility (decker-first vertical slice)?
- Black IC lethality — how protected is the decker against a one-shot kill in MVP?
