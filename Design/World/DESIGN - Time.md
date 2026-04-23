# DESIGN - Time

## Decision

**DECIDED:** Time is **per-minute / real-seconds inside a scene**. Downtime and travel compress; combat uses SR's phase/pass structure.

## Scales of time

| Scale | Used for | Tick rate |
|-------|----------|-----------|
| Combat round | Active fights | 3 sec / round, multiple passes per round based on initiative |
| Scene minutes | Stealth, dialogue, investigation, legwork | 1 real second ≈ 1 in-game minute (configurable) |
| Hour ticks | Exploration, driving, shopping | Player choice: real-time walking vs. "spend N hours" abstraction |
| Day ticks | Sleep, crafting, training in downtime | Fast-forward to morning / N days |
| Week / month ticks | Long-term skill training, recovery, aging | Fast-forward with interrupts |

The player can zoom the clock up or down depending on context.

## Clock interrupts

Fast-forwarding pauses on:
- A contact reaches out (call, message).
- A scheduled payment hits (rent, commlink bill).
- A world event impacts the player (canon event, reputation shift).
- A run offer arrives.
- The player's health/mental needs cross a threshold.
- A crafting / training task finishes.

## Scene time

- Walking, driving, talking all tick scene minutes in real time.
- NPCs around the player follow their schedules.
- Combat pauses scene time on its first round; phase/pass resolves inside the paused envelope.
- Matrix dive: time in the Matrix ticks at hot-VR speed (much faster for the decker); see `Systems/DESIGN - Matrix.md`.
- Astral projection: similar time-dilation considerations.

## Calendar & era transitions

- In-game calendar runs 2050s–2080s.
- Each day has date, day-of-week, news headlines.
- Edition / era transitions are scheduled events on this calendar (see `Setting/DESIGN - Timeline.md`).

## Open questions

- Seasonal / weather mechanics: on or off?
- Real-time vs scene-minute conversion rate default.
- Interrupt fatigue — how to avoid the fast-forward getting paused every other second.
- Long-term PC time skips — let the player retire for a decade, wake up in a changed world.
