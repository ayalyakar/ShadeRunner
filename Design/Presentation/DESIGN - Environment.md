# DESIGN - Environment

## Decision

**DECIDED:** Seattle's canonical environmental phenomena are **first-class mechanical systems**, not just visual flavor. Smog alerts, acid rain, and day/night transitions all produce measurable gameplay effects. Forward-compatible with the post-MVP complex-simulation layer (see `World/DESIGN - Simulation Depth.md`).

Canon anchor: Seattle Sourcebook p.6 (climate), p.19 (smog + acid rain mechanics).

## Weather system

### Cadence
- **Tick rate:** once per in-game hour (aligned to `World/DESIGN - Time.md` real-clock).
- **State:** current temperature, precipitation intensity, smog stage, wind direction, visibility.
- **Seasonal profile:** per-month average / variance derived from canonical climate data.

### Persistence
Weather state persists in save games. A Stage Red smog alert in-progress at save time resumes in-progress on load.

## Stage Red Smog Alerts

Canon: ~90 Stage Red days per year metroplex average; distribution varies by district (coast + cleaner areas lower; Barrens perpetually enshrouded).

### Mechanical effects on Stage Red days

- **Visibility:** reduced — ranged-attack TN +1; Perception checks vs. distance +1.
- **Breather gear requirement:** PC without an equipped **breather** takes 1 Stun box per hour outdoors (canonical SR lung-damage hazard).
- **Breather advantage:** PCs with breathers take no damage; some stealth bonus (breather masks face, obscures ID in crowds).
- **Venue closures:** some venues close or restrict entry (canonical exceptions: Downtown shopping carries on per p.19, venue-specific flags control).
- **Trid notifications:** diegetic commlink alert at stage-change; canonical HUD "Stage Red" banner.
- **Ambient NPC behavior:** crowd density drops; barks shift to coughing / complaining / breather-related.

### Data shape

```yaml
weather_event:
  kind: "smog_alert"
  stage: "red"           # red / orange / yellow / clear
  started_at: "2050-06-12T14:00"
  duration_hours: 18
  affected_districts: ["Redmond", "Puyallup"]
  intensity: 0.8         # 0-1 scales effect magnitudes
```

### District modifiers
- **Cleaner zones (coast, parts of Snohomish):** lower Stage-Red probability; shorter durations.
- **Default zones (Downtown, Bellevue, Everett, Renton, Auburn, Fort Lewis):** baseline.
- **Perpetual-haze zones (Redmond Barrens, Puyallup Barrens):** Stage-Red probability permanent background; residents acclimatized (lower NPC attrition but still mechanical).

## Acid Rain

Canon: Seattle rain is "acid enough to pit and stain buildings and to ruin clothing" (p.19). Still a net air-cleaning positive due to west winds.

### Mechanical effects

- **Gear condition:** armor / clothing / exposed electronics take slow condition damage in rain.
  - Rain damage accrues per in-game hour outdoors.
  - Gear hits 0 condition → loses stat bonuses until repaired.
  - Repair cost scales with gear tier; street vendor < fixer < corporate repair.
- **Coverings:** armored jackets, oilskins, and building-to-building catwalks (Downtown) negate rain damage.
- **Health:** no direct HP damage from standing in rain (it's acid, not deadly-concentrated); only gear effects.
- **Visibility / stealth:** rain obscures LOS slightly (positive for stealth, negative for ranged).

### Data shape
```yaml
weather_event:
  kind: "acid_rain"
  intensity: 0.4
  started_at: "2050-06-12T09:15"
  duration_minutes: 220
```

Gear records carry `acid_rain_resistance: 0..1` (default 0) and `condition_current` / `condition_max`.

### NPC reactivity
- Crowd NPCs react to rain (barks, carrying umbrellas, moving under cover).
- Named NPCs schedule around rain (romance contact's "coffee meet" auto-shifts to a covered venue on rainy days).

## Day / Night cycle

- Lighting, enemy spawn tables, and stealth modifiers shift at canonical thresholds (dawn / noon / dusk / night).
- Metatype dark-vision (Dwarf thermographic, Elf / Ork low-light) applies.
- Certain content (Ork-Underground tour, Puyallup Barrens go-gang roads, Bargain Basement markets) is night-exclusive.

## Temperature

- Tracks Seattle canon: annual mean 5.1°C; July high 21°C; January low -9.5°C.
- Hypothermia risk only at extremes + wet + no shelter (rare; Barrens homeless NPCs most exposed).
- Gear records can flag `cold_weather_gear: true` for winter-appropriate items.

## Canonical prose integration

- Trid weather reports use Woppke the Weatherman's voice profile (recurring BBS persona; see `Data/Lore/Districts/Downtown.yaml`).
- Smog alerts route through the commlink HUD (see `Presentation/DESIGN - UI.md`).

## MVP scope

- Smog alerts: one scripted Stage-Red event during the vertical slice (validates the HUD + breather mechanic).
- Acid rain: weather state running in background; one scripted rain event showing condition damage on the PC's starting armor.
- Day / night: always-on (the clock is always-on).
- Temperature: visual-only at MVP; hypothermia mechanical post-MVP.

## Post-MVP

- Full probabilistic simulation (seasonal distributions, district-specific probabilities, cascading effects).
- Weather-gated content (rare-item vendor only appears on rainy nights, etc.).
- Storm events (thunderstorms, wind storms) with canonical Seattle frequency.
- Weather-aware procgen crowds (fewer people outdoors, different gear choices).

## Open questions

- Exact condition-damage rate from rain (balancing vs. repair economy).
- Breather gear catalogue — single-use filter inserts vs. permanent mask?
- Does Stage Red specifically trigger "Red smog alert" Trid content, or is that separate?
- Weather forecasting — does the PC get advance notice, or only real-time alerts?
- Snow / ice events — canon says rare winter snow is a thing; MVP or post-MVP?
