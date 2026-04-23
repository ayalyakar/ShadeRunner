# DESIGN - Downtime

## Decision

**DECIDED:** Downtime is a first-class part of the game loop, not a skip. Four parallel activity layers:

1. **Full day / night schedule** — hour-by-hour time advancement with meal / sleep / travel time matters.
2. **Training, crafting, relationships** — spend time growing skills, building gear, strengthening bonds.
3. **Hobbies & life goals** — optional non-run pursuits (trid, art, sports, religion, parenting).
4. **Health / mental needs management** — depression, trauma, essence-related conditions, addiction, chronic pain.

See also `Character/DESIGN - Lifestyle.md` and `World/DESIGN - Time.md`.

## Day / night schedule

- The PC has needs: sleep, food, hygiene, hydration, lifestyle routines.
- Default schedule derived from lifestyle tier (Squatter flophouse vs. High-rise condo).
- Player can override specific days.
- Missed basic needs cause status effects that propagate into runs.

## Training & crafting

- **Training** — skill progression via downtime (see `Character/DESIGN - Progression.md`).
- **Crafting** — gear, ammo, foci, programs, drones, vehicles; per-system crafting lives in the respective system docs.
- **Alchemy / enchanting** — see `Systems/DESIGN - Magic.md`.
- **Decker loadout** — see `Systems/DESIGN - Matrix.md`.
- **Drone / vehicle modification** — see `Systems/DESIGN - Rigging.md`.

Training and crafting all consume time and sometimes materials. They interrupt on world events.

## Relationships

- Spending time with contacts raises Loyalty (see `Social/DESIGN - Contacts.md`).
- Romances can form, deepen, rupture.
- Family ties — living relatives, exes, children — each tracked as contacts.
- Bonds produce **mechanical gifts**: legwork freebies, better prices, emergency extraction, information leaks.

## Hobbies & life goals

- Optional long-term tracks: collect trideos, master a game, run a charity, restore a classic vehicle, raise a kid, build an art career on the side.
- Hobbies grant **flavor** and small mechanical rewards (stress relief, contacts through hobby communities).
- A long-running runner's hobbies are part of who they are — the sim supports "this character became obsessed with orchid cultivation".

## Health & mental needs

- Physical injuries heal over real time; better lifestyle / Doc Wagon / magic accelerates.
- **Mental health**: stress, trauma, addiction, essence-related depression.
- **Trauma events**: seeing a contact killed, losing Essence badly, running out of magic, failing a PC you care about.
- Mental conditions have mechanical expression (dice penalties, dialog restrictions, impulse triggers) and require treatment (therapy, medication, magic, time).
- Essence-linked psychological effects connect cyberware loss and long-term wellness.

## Cadence & player control

- The player chooses which activities fill the day.
- A **week planner** UI lets the player batch days of training or relationship-building.
- The clock interrupts on significant events (see `World/DESIGN - Time.md`).

## Open questions

- How heavy should survival pressure be — chore avoidance is paramount.
- Passive needs vs. active management: how much of each day should feel "automated".
- Mental health mechanics tone — important to handle respectfully and without trivialization.
- Children as long-term PCs-in-waiting — is parenting a protagonist-switch feeder track?
