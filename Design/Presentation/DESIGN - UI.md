# DESIGN - UI

## Decision

**DECIDED:** **Multi-layer, context-dependent UI.** Different UI language per view:

- **Tabletop-dense data surfaces** for character sheet, inventory, stat inspection, combat log.
- **Clean diegetic AR / commlink UI** for in-world messaging, maps, contact roster.
- **Minimal HUD + investigation board** for legwork, case-boards, detective work.
- **Terminal / text UI** for BBS and light Matrix work.
- **Matrix deep-dive UI** — distinct UI that feels like cyberspace.

Each UI layer is internally consistent; layers don't fight each other.

## Guiding principles

- **Right tool per job.** Mechanics-heavy moments get mechanics-heavy UI; immersion-first moments get invisible UI.
- **Inspectable on demand.** Dice math and stat derivations are always accessible via hover / tooltip (see `Systems/DESIGN - Combat.md`).
- **Diegetic where sensible.** Commlink notifications, contact calls, BBS browsing feel like using the character's hardware.
- **Keyboard-first, but input-abstract.** Every key action can be rebound.
- **High information density available.** Tabletop enthusiasts get rich sheets; casual players get summary views with drill-down.

## UI surfaces

### Character sheet
- Full attributes, skills, qualities, gear, Essence, Magic, Resonance.
- Tabbed: Stats, Skills, Gear, Contacts, History, Qualities, Magic/Resonance.
- Live pool computation previews.

### Combat HUD
- Initiative track down the side.
- Active character panel: actions, movement budget, cover state.
- Tooltip-on-demand dice math.
- Collapsible combat log.

### Commlink (diegetic)
- In-world phone-like interface for contacts, messages, calendar, maps, news feed.
- Pops up when a call / notification fires.
- Persistent toolbar during exploration.

### BBS / terminal
- Text-first, command-line feel.
- Full-screen when focused.
- Quotes shadowland aesthetic for flavor.

### Investigation board
- Drag-drop cards (evidence, suspects, leads, locations).
- Connect cards with labeled edges to form theories.
- Skill checks unlock inferences.

### Matrix deep-dive
- Dedicated 3D UI — host topology, IC icons, program bar, persona stats.
- Visually distinct from all other views; era-skinned.

### World map
- Zoomable: district → neighborhood → street.
- Overlays: faction influence, heat heatmap, contact locations, job markers.

## Accessibility (minimum)

- Subtitles always-on default.
- Remappable keys.
- Scalable font.
- Colorblind-safe palette.
- See `Gameplay/DESIGN - Difficulty.md` for broader accessibility status.

## Open questions

- Controller support — tabled (PC keyboard-first).
- Mobile-companion commlink app (as a real app) — cool idea, deferred.
- How much of the character sheet to expose in the HUD vs. dedicated screen.
- Panel-management model (docked panels vs. full-screen overlays).
