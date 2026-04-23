# DESIGN - Vision

## Pitch

A personal, solo-developed Shadowrun CRPG set in the Seattle metroplex between 2050 and 2064. Baldur's Gate 3 / Divinity: Original Sin II-style isometric turn-based party-of-one combat, classic "shadowrunner for hire" structure, and a fully-unlocked NSFW register co-equal with combat as a design pillar. No commercial release, no platform storefront, no content filters.

## Pillars

1. **Shadowrun 1E flavor, modern playability.** Lore and voice stay period-authentic to SR1E (FASA 1989–1990). Mechanics can borrow later-edition rulings where they are cleaner to play.
2. **Seattle metroplex is the world.** Redmond is the MVP anchor. Other districts stub in, densify as the project grows.
3. **All four SR pillars are playable.** Combat, Matrix, Magic, Rigging are all MVP-scope in character creation. Street Samurai is built first; the others follow with the same rigor.
4. **Shadowrunner for hire.** The core fantasy is episodic: meet a Johnson, take a run, get paid, build rep, burn contacts, pay rent.
5. **NSFW as a pillar, not a flavor.** Adult content is first-class: sex, sex work, BTL chips including adult chips, drug addiction mechanics, graphic violence, torture, body horror, illustrated-explicit register. No toggle.
6. **Tone range: gritty noir × pulpy neon × romance/NSFW.** Scenes pick the register that fits. The game is not monotonal.
7. **Solo-dev discipline.** No abstraction or feature exists without a concrete plan to ship it. See `DESIGN - Production.md`.

## Scope anchors

- **Genre:** CRPG, turn-based, solo PC, isometric.
- **Target length:** 50+ hours main path (ambitious for solo; see Production for risk).
- **Protagonist:** blank-slate character creation (metatype, archetype, stats, background).
- **Archetypes MVP-playable:** Street Samurai, Physical Adept, Decker, Full Mage / Shaman.
- **Saves:** save-anywhere. No ironman.
- **Engine:** Godot 4, GDScript, 3D-rendered isometric with camera lock.
- **Target OS:** Windows.
- **Runtime LLM:** never. Dev-time LLM: writing drafts, image generation, code assist, TTS.

## What this is NOT

- Not a commercial release. No EULA, no storefront, no licensing constraints.
- Not multiplayer.
- Not a live-service game.
- Not a strict tabletop SR1E simulator. Mechanics serve the game, not the ruleset.
- Not a game that filters dark content. See `Meta/DESIGN - NSFW.md`.

## Tone / voice

- Noir default, with permission to drift pulp and satirical depending on scene.
- NSFW scenes carry a distinct register: explicit, unhedged, character-true. Not leering; not coy.
- Writing aims for adult literacy. Dialogue trusts the player.

## Open questions

- Exact "feels like Shadowrun" acceptance test. Metrics vs. playtest judgment.
- Art target fidelity — Godot's 3D-iso range from stylized-cheap to cinematic-AAA.
- Party-of-one vs. scene-only companions — does the PC ever directly control an NPC in combat?
- How explicit does NSFW art get at MVP vs. placeholder for later pass?
