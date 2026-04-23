# DESIGN - Matrix

## Decision

**DECIDED:** Matrix is a first-class subsystem with **two representations**:

1. **Separate 3D / VR cyberspace layer** for deep dives (SR1–3 vibe, keeps era flavor).
2. **Terminal / text-based** interface for BBS, shell commands, diegetic computing.

Non-decker PCs handle the Matrix through three fallbacks:

- **Abstracted 'security bypass' skill checks** (mini-puzzles or rolls via Electronic Warfare / Hacking skill).
- **Hiring NPC deckers via contacts** (see `Social/DESIGN - Contacts.md`) when a real run needs deep access.
- **Skill gate** — some missions truly require a decker; without one, the player chooses a different approach or fails.

No auto-pilot agent software as a replacement for a decker.

## Era handling

Matrix mechanics differ by era:
- **SR1–3 (wired Matrix):** cyberdecks, jackpoints, dataline/trodes, full VR dive. Running the Matrix means sitting down and jacking in.
- **Post-Crash 2.0 (SR4):** wireless Matrix, commlinks, AR overlay everywhere, new cyberdeck scarcity. Technomancers emerge.
- **SR5 era:** hosts, grids, Public/Corporate, deckers vs. technomancers, new program economy.
- **SR6 era:** current canon.

Edition transitions can obsolete old gear and require the player's decker contacts to upgrade too.

## Deep-dive layer

- Dedicated 3D cyberspace (SR1-3 aesthetic as default, with era-dependent skin).
- **Personas** — PC's icon, customizable.
- **Hosts** — corp / gov / gang hosts, each with architecture and IC.
- **Programs** — Attack, Sleaze, Data Processing, Firewall, Exploit, Browse, etc.
- **IC (Intrusion Countermeasures)** — monster-like entities with behaviors (Patrol, Probe, Killer, Black IC).
- **Dumpshock / biofeedback** when the decker's persona is killed (real stun/physical damage).

## Terminal layer

- Used for non-dive Matrix work: BBS browsing, email triage, shadowland threads, script-kiddie tasks.
- Visible as a commlink app with a terminal shell.
- Commands are diegetic ("grep the paydata for 'Ares Fairlight'") and resolve via skill rolls behind the scenes.

## Matrix time dilation

- Hot-VR dive: time in the Matrix ticks **fast** relative to meat time (SR-canonical).
- Cold-VR / AR: roughly 1:1 with meat.
- This means a decker can resolve a lot while the meat team stands in a hallway — but dumpshock is waiting for them if it goes wrong.

## Security bypass (non-decker)

- When a maglock / camera / sensor is in the way and the PC isn't jacked, a skill-check puzzle opens.
- Puzzle types: pattern sequence, signal tracing, password pivot, cable splicing, ice-pick timing.
- Puzzles are gated by Electronic Warfare / Hacking skill; low skill can't attempt.
- Success == bypass; failure == alarm / damage / traceable evidence.

## Hiring a decker

- A contact with Connection in the decker scene can provide a specialist for a run.
- Pay or favor cost; specialist skill tied to the contact's tier.
- Specialist is an NPC whose stats and equipment the player can inspect; they act as an ally during the run.
- Specialist can betray, die, or refuse escalation; relationship affects pay and reliability.

## Open questions

- How much of deep-dive is turn-based like combat vs. a separate real-time pacing.
- Interaction with physical combat simultaneity — splitscreen? Fast context switch?
- Technomancer mechanics — full Resonance / Submersion paths with sprites and streaming. Separate or unified UI?
- How many hand-crafted hosts vs. procedural host generation.
