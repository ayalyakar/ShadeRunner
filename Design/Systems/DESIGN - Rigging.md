# DESIGN - Rigging

## Decision

**DECIDED:** Rigging is a first-class subsystem with full depth across all four capabilities:

1. **Jumped-in real-time drone control** (primary perspective swaps to the drone).
2. **RCC command console** — multi-drone autonomous orders.
3. **Vehicle customization / chop shop** — build, tune, mod.
4. **Drone construction & programming** — assemble from parts, write pilot autosofts, tune behavior.

## Jumped-in control

- Full perspective swap to drone's camera / sensor feed.
- PC's meat body becomes a vulnerable lump; needs safe location or spotter.
- Drone dodges, shoots, flies in real-time (within the turn-based round structure: the jumped-in drone acts on its own Initiative).
- Drone's Initiative gets bonuses from wired commlink / sim module / control rig grade.
- Dumpshock if the drone is destroyed mid-jump.

## RCC command console

- Rigger Command Console: the rigger's workstation.
- Issues orders to multiple drones simultaneously.
- Drones follow autopilot / autosoft logic when not jumped-in.
- Orders include: Patrol, Escort, Attack-on-sight, Scout-target, Return-home, Self-destruct.
- Matrix-dependent — RCC channel can be jammed / hacked.

## Vehicle customization (chop shop)

- Every vehicle has stats: Acceleration, Speed, Handling, Armor, Body, Pilot, Sensor, Mod slots.
- Mod slots: Powertrain, Protection, Weapons, Body, Electromagnetic, Cosmetic, Special.
- Mods require Matchbox (facility), tools, parts, time.
- Reverse engineering and part harvesting — strip a wrecked car for parts.
- Faction / era availability rules (getting a Ferret scout drone in SR1 is harder than SR5).

## Drone construction & programming

- Drones from parts: chassis, motor, sensors, weapons, armor, autosoft slots.
- Autosofts — skill software for drones (Clearsight, Targeting, Maneuvering, specific doctrines).
- Behavior tuning — adjust priorities, threshold triggers, fallback behavior.
- Programming takes downtime; tuning quality depends on Hardware + Software skill.

## Integration with other systems

- **Matrix:** RCC runs on Matrix; drones can be hacked away (Brick / reset / suborn).
- **Combat:** drones appear as combat actors on their own Initiative.
- **Magic:** spells can affect drones (Control Rig is just a computer, not magical — most spells fizzle, but some work).
- **Social:** drones change the social calculus (noticeable, scary, heat-raising).

## Vehicles as gameplay

- Chases, roadblocks, pursuits use the same combat-pass system.
- Smuggling runs feature vehicle-centric gameplay.
- Commuting between districts uses vehicles diegetically (fuel, routine, inspection).

## Open questions

- Jumped-in perspective details — full swap to first-person-drone, or windowed HUD?
- Drone pathfinding at sprawl scale — expensive.
- Autosoft market and pricing balance.
- Vehicle garages, impounding, theft — property mechanics.
