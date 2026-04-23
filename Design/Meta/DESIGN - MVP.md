# DESIGN - MVP

## Decision

**DECIDED:** MVP is a **full-run vertical slice** — Meet → Legwork → Execute → Payout, end-to-end, for any of the four playable archetypes, in **Redmond**.

MVP is **shippable to self**: no placeholders in the critical path. A missing feature means the feature is out of MVP; a present feature means it works.

## Scope

### District
- **Redmond only.** One hand-built neighborhood walkable in isometric 3D. Exact neighborhood TBD (candidates: a Touristville neighborhood or a Redmond Barrens sub-area; decided once Redmond pages are ingested).
- Other Seattle districts exist as canonical `Data/` stubs only; not visitable.

### Archetypes (all four playable at MVP)
- **Street Samurai** — combat archetype. Built first (the combat engine is the highest-risk subsystem).
- **Physical Adept** — magical combat; reuses combat scaffolding with a magic overlay.
- **Decker** — Matrix archetype. Requires Matrix subsystem at MVP depth.
- **Full Mage / Shaman** — spellcasting. Requires Magic subsystem at MVP depth.

Each archetype has **one MVP-playable build** — not the full skill/spell/program tree. More builds land post-MVP.

### Chargen
- Blank-slate character creation: **karma point-buy** across metatype, attributes, skills, resources. No priority table.
- **Metatypes at MVP: all five SR1E core** — Human, Elf, Dwarf, Ork, Troll.
- **Attributes:** SR3E/4E model (Agility split from Quickness; Body, Agility, Reaction, Strength, Charisma, Intelligence, Logic, Willpower + Essence, Magic).
- **Skills:** SR1E skill tree, consolidated (redundant small-item skills merged; SR1E flavor retained).
- **Starting gear:** minimal playable catalogue (~15–30 items covering one weapon per category, armor, basic runner kit).
- **Cyberware:** minimal starter kit available at chargen (smartlink, wired reflexes 1, dermal 1, cyberears / cybereyes basics). Essence cost applies. Full catalogue post-MVP.

### Run structure
- **Meet** — fixer-to-Johnson in a Redmond venue (bar / hotel / safe house).
- **Legwork** — at least one dialogue-skill beat and one perception / data-search beat.
- **Execute** — mission environment. Must be completable via combat *or* non-combat path, with at least one branch (stealth / hack / magic / social).
- **Payout** — dialogue, karma, rep, nuyen. Consequence imprinted on faction / contact state.

### Concrete MVP run
- **Type:** **Retrieval** (steal a specific item). Classic SR opener; clean goal; supports all four archetype paths.
- **Johnson:** **Corporate Mr. Johnson** — mid-tier corp fixer hiring the PC for a data-chip / prototype retrieval. Covers the widest run-type surface and sets up corp-antagonist tension early.
- **Fixer:** **Warm, seasoned Redmond fixer** — older, gruff, cares about the PC more than she admits. Connection ~3–4. Steady job supply. Lives / works in Redmond. She introduces the Johnson.
- **Target:** specific item in a specific corp-adjacent location in Redmond (exact target to be decided once the Redmond chapter ingests).
- **Paths:**
  - **Combat:** front-door, shoot through guards.
  - **Stealth:** back entry, avoid detection.
  - **Decker:** jack into the host, grab the item remotely or disable security for physical entry.
  - **Magic:** spirit-scout, invisibility / influence, magical entry.
  - Minimum two paths playable for any archetype (their class path + at least one shared approach).
- **Romance contact:** **Fellow runner encountered on the job** — met during Legwork or Execute as a friendly / rival face. Romance escalates across subsequent downtime beats. One complete romance arc (meet → rapport → first explicit scene) shipped in MVP.

### Systems MVP depth
- **Combat:** turn-based, **phase-pass initiative** (high-Reaction acts multiple passes per round), **SR1E d6 exploding dice pool** resolution (count successes vs. target number), **square grid**, full cover + line-of-sight, **SR1E wound boxes (Physical + Stun tracks)** with dice-pool penalty. See `Systems/DESIGN - Combat.md`.
- **Matrix:** **abstract minigame** surface (dedicated Matrix scene), **SR1E wired Matrix baseline** with post-Crash wireless drift eligible post-MVP. One decking loop — host, IC opposition, file retrieval or node control, jack-out consequences. See `Systems/DESIGN - Matrix.md`.
- **Magic:** **Hermetic and Shamanic** traditions only at MVP; other traditions post-MVP. **Spellcasting + spirit summoning** (drain, line-of-sight, spirit services). See `Systems/DESIGN - Magic.md`.
- **Rigging:** **NOT in MVP.** Deferred. Rigger archetype is post-MVP.
- **Social / contacts:** one fixer, one Johnson, one contact archetype (e.g. fence), dialogue with skill checks. **One romance-eligible named contact** at MVP (validates the romance-scene pipeline end-to-end).
- **Economy:** monthly rent at Low tier (2,000¥/mo per prior calibration), payout → karma / rep / nuyen loop. Sex work / BTL chip sale / drug sale as alt income channels working in parallel with run payouts.
- **Addiction:** **simulated** (tolerance, addiction, withdrawal) for drugs and BTL chips. Mechanical, not just narrative.
- **BTL:** BTL chips as **consumable items** at MVP — buy, consume, sell, with short buff/debuff effects and addiction risk. Chip-library authored. BTL-studio runs and full BTL career path are post-MVP.
- **NSFW:** at minimum, one illustrated-explicit scene in the vertical slice (sex scene with the romance contact, a BTL-studio encounter, or a wetwork scene). Validates the NSFW pipeline end-to-end. **Art fidelity at MVP:** ship diffusion-drafted still illustrations as-is (human-curated). Full animated sex scenes are a stated post-MVP goal.

### Presentation / UI
- Isometric 3D with fixed camera.
- **Diegetic cyber-UI register** — HUD, menus, and overlays styled as in-world commlink / ARO overlays.
- **Commlink as always-accessible hub** (hotkey-open), containing Messages / Calls / Map / Inventory / Character sheet / Matrix / BBS / Trid / Journal / Options tabs.
- **Dialogue UI:** portrait + dialogue box at MVP. Skill-gated choices visible with inline tags (e.g. `[Etiquette 4]`, `[Sorcery]`). Full 2D illustrated dialogue scenes are a **post-MVP** goal.
- **Inventory:** weight / encumbrance limited. No slot grid.
- **Map:** per-district local map + mini-map HUD.
- **Tutorial:** contextual tooltips on first encounter with each system. No scripted tutorial level.
- **Accessibility at MVP:** subtitle customization (size / background / speaker labels) + text scale + dyslexia-friendly font option. Other a11y features post-MVP.
- **Input:** mouse + keyboard, rebindable. Controller support post-MVP.
- **Save-anywhere.** Godot-native save format; manual slots + autosave + quicksave.
- **Real-clock time** (in-game minutes). Monthly rent cycle. NPC schedules respected.

### Out of MVP scope
- Rigging.
- Multi-district travel.
- Era transitions (2050 fixed at MVP).
- Multiple MVP runs (single run; procgen runs are post-MVP).
- Full voice acting (TTS / text-only at MVP).
- Beyond-core metatypes (shapeshifters, drakes, etc.).
- Companion control in combat.
- Cutscene cinematics.

## Why these choices

- **Redmond:** classic SR starting ground, deep canon baggage, lawless Barrens → plenty of run content; the prior pass established it as anchor.
- **All four archetypes at MVP:** the project's fantasy is "Shadowrun", and Shadowrun isn't one archetype. Accepting the cost.
- **Street Sam first:** combat is the highest-risk subsystem. Validate it with the simplest archetype, then plug magic/Matrix onto the scaffolding.
- **One run:** forces a complete vertical slice instead of broad shallow coverage.
- **NSFW in vertical slice:** NSFW is a stated pillar, so it must survive MVP end-to-end, not be promised for later.

## Acceptance criteria

1. Start new game → chargen (any of four archetypes) → wake up in Redmond.
2. Receive a fixer call → Johnson meet → accept a run.
3. Legwork beat (dialogue + perception + optional NSFW venue).
4. Execute the run end-to-end via at least two different archetype paths (combat and one other).
5. Payout; karma, rep, nuyen applied.
6. Rent clock advances; save, quit, reload preserves state.
7. NSFW pipeline has at least one illustrated-explicit scene hooked in and working.

## Post-MVP priorities

1. **Rigging subsystem v1.**
2. **Additional Redmond neighborhoods.**
3. **Second district opened (Downtown or Tacoma).**
4. **Procgen side runs.**
5. **Era-transition system (2050 → 2064).**
6. **Deeper NSFW pipeline (romance arcs, brothel hub, BTL studio runs).**
7. **Companion-in-combat control.**

## Open questions

- Which Redmond neighborhood is hand-built? Picked once Redmond pages are ingested.
- First run type (retrieval / protection / extraction / sabotage / NSFW-primary)?
- Magic tradition coverage at MVP (hermetic + shamanic only, or all published)?
- Matrix archetype viability in MVP depth — is one decking loop enough to make Decker feel distinct?
- NSFW scene placement in the vertical slice — optional Legwork side path, or mandatory?
