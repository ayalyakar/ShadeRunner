# DESIGN - Multiplayer

## Decision

**DECIDED:** **Strictly single-player.**

No netcode, no co-op, no async sharing, no MMO-lite. The game is a private simulation for one person.

## Rationale

- Solo developer; netcode is a multi-year investment alone.
- Sim design assumes one player's time axis and one perspective; multi-player breaks that.
- Deep simulation + long timeline + save-scum freedom are all easier to support single-player.
- No commercial pressure to add it.

## Implications

- World simulation is authoritative locally; no server.
- Saves are local files (see `Technology/DESIGN - Persistence.md`).
- No anti-cheat considerations.
- No leaderboards, achievements-as-retention, or social pressure systems.
- Modding remains closed for now (see `Meta/DESIGN - Modding.md`) but has no MP constraint.

## Possible future (explicit non-goals for now)

Deferred and not planned in any current milestone:
- Async run sharing (export/import character snapshots) — interesting but not a priority.
- Shared spectator mode — same.
- Seed sharing for procgen districts — cheap if ever wanted.

None of these are committed.

## Open questions

- None.
