# DESIGN - Time

## Decision

**DECIDED:** **Real-clock time** — the in-game clock ticks in minutes. Date, hour, and minute all visible and meaningful. **Monthly rent** as a lifestyle pressure (SR-classic). NPC scheduling, venue availability, shop opening hours, crime ambient events all respect the clock.

## Clock model

### Units
- **Minute** — base tick. Scenes, combat turns, dialogue beats elapse in game-minutes.
- **Hour / Day / Week / Month / Year** — derived.
- **Era start:** 2050 at chargen (Seattle Sourcebook year).
- **Era drift:** canonical — clock can advance past 2064 if the campaign runs long. See `Setting/DESIGN - Canon.md`.

### Time pass per activity (indicative MVP)
| Activity | In-game time |
|---|---|
| Combat encounter | 1–5 minutes |
| Dialogue scene | 5–15 minutes |
| Stealth infiltration sequence | 15–30 minutes |
| Matrix sequence | 5–20 minutes |
| Cross-neighborhood travel | 15–45 minutes |
| Cross-district travel | 1–2 hours |
| Shopping beat | 10–30 minutes |
| Training downtime | 4 hours |
| Sleeping | 6–10 hours |
| Long rest (full recovery) | 8+ hours |

Exact values tuneable per activity in MVP calibration.

## Schedules

- **Named NPCs** declare `schedule:` in their Data file:

  ```yaml
  schedule:
    weekday:
      06:00: "home"
      09:00: "work_venue"
      18:00: "favorite_bar"
      23:00: "home"
    weekend:
      10:00: "home"
      13:00: "favorite_bar"
      ...
  ```

- **Venues** declare open hours:

  ```yaml
  open_hours:
    weekday: { open: "11:00", close: "03:00" }
    weekend: { open: "14:00", close: "05:00" }
  ```

- **Encounters / ambient events** can be time-gated: gang turf is livelier at night, street doc takes appointments by day, BTL studios shoot overnight, brothels open at dusk.

## Day / night cycle

- Visual: lighting + sky changes in 3D scenes per hour of day.
- Gameplay: stealth modifiers (dark vision metatypes / cyberware become powerful at night); Lone Star patrol density shifts.
- Ambient NPCs: fewer mundane NPCs at night, more dangerous ones.

## Economic clock

- **Rent: monthly.** Lifestyle tier (Street / Squatter / Low / Middle / High / Luxury) deducts rent on the 1st of each month. Missing rent demotes lifestyle one tier and fires consequence events (eviction, lost fixer retainer, commlink cut, contacts drop).
- **Contact retainers:** monthly line items for on-call contacts (street doc retainer, fixer retainer).
- **Shop restock:** weekly cadence per shop. Rare stock rolls on month boundaries.
- **Addiction ticks:** BTL / drug addiction advances / regresses on a daily clock when the PC is not using. Skipping too long triggers withdrawal effects.

## Clock UX

- **HUD clock** shows current date and time prominently.
- **Time-advance preview** on actions: "Sleep 8 hours? Time will advance to Thursday 07:00, rent due in 3 days."
- **Run deadlines:** some Johnson jobs carry a deadline (e.g. "deliver by 23:00 Thursday"). Missing it reduces payout or fails the run.
- **Appointments:** named NPCs may schedule with the PC ("come back Monday evening"). Missing an appointment has narrative weight.

## Save points and time

- Save is available at any in-game minute. The clock is part of the save state.
- Loading restores to exactly that minute.

## Post-MVP / future

- **Seasons / weather** — weather roll per day, seasonal clothing markup, winter vs. summer ambient.
- **Era transitions** — canonical events fire at specific in-game dates (Crash 2.0, specific corp takeovers, magical events). Requires era-drift system design.
- **Long-term NPC aging** — matters only if the campaign stretches years.
- **Player aging** — ork / dwarf / troll lifespan edge cases if era drift is long. See `Character/DESIGN - Aging.md` (future).

## Open questions

- Minute precision vs. hour precision — do we show minutes on the HUD, or just rough hour?
- Does sleep auto-advance or require an explicit action?
- Time-gated NSFW / venue content — does a brothel need specific hours, or always open at MVP?
- Is there a maximum campaign length cap, or does the clock run forever until PC death / retirement?
- Rent failure mode — eviction is harsh; do we add warning periods?
- Does combat pause the real clock entirely, or tick at scaled rate?
