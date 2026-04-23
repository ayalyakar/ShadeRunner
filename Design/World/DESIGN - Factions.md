# DESIGN - Factions

## Decision

**DECIDED:** All major Shadowrun faction classes are **first-class simulation actors** with agendas, resources, and ability to act on the world autonomously.

## Faction classes (all in scope)

1. **Megacorps (AAA and AA).** Ares, Saeder-Krupp, Renraku, Mitsuhama, Aztechnology, NeoNET (until the fall), Evo, Shiawase, Wuxing, Horizon, Spinrad, and AA tier. Internal politics matter.
2. **Gangs & organized crime.** Yakuza, Triads, Mafia, Vory, street gangs (Ancients, Spikes, Halloweeners, etc.), policlubs, smuggler rings.
3. **Governments & law enforcement.** UCAS, CAS, NAN, Tír Tairngire/Tír na nÓg, Aztlan, European nations; Knight Errant, Lone Star, Doc Wagon.
4. **Magical & esoteric.** Great Dragons, immortal elves, secret societies (Atlantean Foundation, Illuminates of the New Dawn), awakened cults, Draco Foundation.

## What a faction tracks

- **Agendas:** goals at multiple time horizons.
- **Resources:** money, personnel, assets, intel, magical power.
- **Holdings:** districts, facilities, officers, subsidiaries.
- **Relationships:** allies, rivals, active disputes, pending contracts.
- **Public posture:** what the trid/BBS says about them.
- **Heat:** how much attention they're under.

## Faction actions

Factions act on ticks (daily at the sprawl layer, weekly at the global layer):
- Pursue agendas (acquire, expand, eliminate rivals, lobby).
- Hire runners for deniable ops.
- React to player actions and to other factions' actions.
- Respond to canon events (e.g. Crash 2.0 rewrites corp holdings).

## Player interaction

- Player has a **reputation** and **history** with each faction (see `World/DESIGN - Reputation.md`).
- Player can be **hired by**, **betray**, **ally with**, **undermine** any faction.
- Long-term player pressure can genuinely shift faction fortunes within the constraints of canon anchors (see `Setting/DESIGN - Canon.md`).

## Per-faction data

Canonical faction entries live under `Data/Lore/Factions/<Name>.yaml` (see `Setting/DESIGN - Canon.md` for ingestion policy). Each entry records type, sources, per-district presence, leadership, game-presence tier (ambient / MVP / post-MVP), and narrative hooks. Faction-NPC links cross-reference `Data/Lore/NPCs/`.

## Open questions

- Faction AI sophistication — goal-oriented planner, utility AI, or scripted personalities?
- How many factions can the sim track before it becomes unreadable to the player?
- Intra-faction politics — one monolithic actor per faction, or multiple executives with competing agendas?
- Secret societies: how does the player discover they exist at all?
- Sub-faction handling: a district-level Mafia branch with its own Don and capo is a distinct sim actor from "Seattle Mafia" at large — how deep does the nesting go?
