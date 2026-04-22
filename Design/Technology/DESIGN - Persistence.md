# DESIGN - Persistence

## Decision

**DECIDED:** Hybrid persistence — full event log of consequential NPC actions, combined with zonal simulation so that distant regions run in abstracted form while the player's current region is simulated in detail.

## Save model

- **World seed** — deterministic starting state of sprawl, factions, canonical NPCs at game start year.
- **Event log** — append-only log of every consequential change: deaths, promotions, contract outcomes, reputation shifts, canonical timeline events.
- **Zonal snapshots** — periodic snapshots of each zone's state so replay isn't required from the beginning.
- **Player state** — PC stats, inventory, karma, relationships, current scene.

Loading = latest snapshot + replay of subsequent events (bounded). Saving is cheap (append); the world is reconstructible.

## Zonal simulation

- **Active zone** (where the PC is): full NPC ticks, per-minute time, detailed sim.
- **Adjacent zones**: reduced tick rate, fewer agents modeled individually.
- **Distant zones**: statistical aggregate — "how many runs occurred in Tacoma this week" rather than per-NPC.
- Promotion and demotion of zones happens when the player moves, in the background.

When the player visits a previously-abstract zone, the zonal snapshot is re-hydrated into detailed state; any player-relevant history is retained.

## Canonical-event handling

Canon timeline events (Crash 2.0, Dunkelzahn's will, etc.) are scheduled in the event log regardless of zone fidelity. They fire at canonical dates unless the player has a "canon unless player acts" flag flipped for that event (see `Setting/DESIGN - Canon.md`).

## Save file shape (draft)

```
save/
  world.seed
  events.log            # append-only, binary
  snapshots/
    zone_redmond.snap   # one per zone
    zone_downtown.snap
    ...
  player.state
  meta.json             # version, character id, timestamp
```

## Size & performance

- Event log size is the main concern. Mitigation: coarse events only (nothing ambient); compact binary encoding; periodic compaction that collapses superseded events.
- Snapshots: dedicated save step triggered on zone transition and every X in-game days.
- Saves are free anywhere (see `Gameplay/DESIGN - Saves.md`) — but saving itself is cheap because it's a flush, not a dump.

## Open questions

- Exact event schema (will be iterated heavily).
- Save-file compatibility across versions: migration scripts or versioned snapshots?
- How to expose "what happened while I was away" to the player without overwhelming them? (Newspaper? Contact gossip? Commlink feed?)
- When the player time-travels via aging (decades pass), how is the event-log explosion handled?
