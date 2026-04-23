# DESIGN - UI

## Decision

**DECIDED:** Diegetic cyber-UI register — HUD, menus, and overlays styled as in-world commlink / augmented-reality object (ARO) surfaces. **Always-accessible in-world commlink** as the primary non-game-action hub. **Portrait + dialogue-box** for conversations at MVP (with full 2D illustrated scenes as a post-MVP upgrade). **Skill-gated choices are visible** (tagged inline). **Contextual tooltips** for tutorialization — no scripted tutorial level. **Weight / encumbrance** inventory model. **Per-district local map + mini-map** for navigation.

## Visual register

- **Diegetic cyber:** UI panels look like in-world ARO overlays projected from the PC's commlink / cybereyes. Neon accents, glassy panels, pixel-imperfect glitches, scanlines on dense text readouts.
- **Readable at glance:** even while in-universe, UI passes CRPG-readability basics (high contrast, text hierarchy, minimum-size fonts).
- **Scene-tonal tweaks:** UI adopts scene tone (combat = red-tinted HUD; Matrix = green wireframe; romance = softer warm palette; blood-magic horror scenes = desaturated red/black).

## Hub: the commlink

- **Always-accessible via hotkey** (default `Tab`).
- **Tabs inside the commlink:**
  - **Messages** — dialogue history, text from contacts, Johnson briefs.
  - **Calls** — active / missed / recent (calling a contact opens a dialogue scene).
  - **Map** — per-district local map + mini-map (on by default during exploration).
  - **Inventory** — gear, cyberware, implants, carried items.
  - **Character sheet** — stats, skills, karma, rep.
  - **Matrix** — tile showing Matrix alerts if any; jack-in via a physical jackpoint starts the Matrix scene.
  - **BBS / Shadowland** — posts, job-board hits, news.
  - **Trid feed** — in-world news / ads / entertainment channel.
  - **Journal** — active run, contacts met, places discovered.
  - **Options / Save** — system menu.

## Dialogue UI (MVP: portrait + box)

- **Layout:** speaker portrait (left or right, per convention), dialogue text box, player option list.
- **Portrait:** diffusion-generated per named NPC, reactive emotive variants (see `Presentation/DESIGN - Art Direction.md`).
- **Skill-gated choices:** option lines tag their requirement inline, e.g.:
  ```
  [Etiquette 4] "I know how this dance goes — what's the real budget?"
  [Intimidate 5] "Try me, chummer."
  [Sorcery]       Cast Analyze Truth on them.
  [Streetwise 3]  "Your accent — you don't run with the locals."
  ```
- **Result preview:** hovering a skill option shows dice pool and TN.
- **Text speed / skip:** adjustable text-reveal rate; skip to end on player action; full-skip of scene if flagged `skip_safe`.

### Post-MVP dialogue upgrade
**Full 2D illustrated scene per conversation.** Every dialogue beat displays a comic-noir illustrated panel. Massive art scope; flagged as post-MVP goal. See `Presentation/DESIGN - Art Direction.md`.

## Combat HUD

- **Top bar:** turn order / pass counter, round number, current actor.
- **Bottom bar:** action economy (simple / complex used), Reaction-initiative indicator, weapon hotkey row.
- **Hover-preview:** attack preview on target — TN, dice pool, expected damage, cover indicator, range band.
- **Dice visualization:** animated exploding d6 roll in a floating panel; slow / fast / off settable per taste.
- **Enemy info:** hover an enemy for their visible stats (wound boxes, perceived threat, armor estimate if known).

## Matrix UI

- **Separate scene** with abstracted node graph (see `Systems/DESIGN - Matrix.md`).
- **Persona panel:** Bod / Masking / Sensor / Evasion stats, active utilities, deck rating.
- **Action palette:** available utilities for current node, costs, TNs.
- **Alert meter:** Green → Yellow → Red → Black. Visible to player.
- **Meat-body HUD** in a corner — the PC's physical status while jacked in (health, proximity alerts).

## Inventory

- **Weight / encumbrance limited.** Each item has weight; PC's carry capacity = Body × multiplier (tuned). Overburdened = Quickness / Agility reduction.
- **Slot-free:** no artificial slot grid. Weight is the sole constraint.
- **Equipped slots:** weapons (primary / secondary / melee), armor, implants, cyberdeck, quick-use items (BTL chip slot, drug slot, healing-kit slot).
- **Weapon quick-swap** during combat (simple action).
- **Bulk management:** stash at home (PC's apartment has storage). Fence excess loot.

## Character sheet

- **Stats block:** Body / Agility / Reaction / Strength / Charisma / Intelligence / Logic / Willpower / Essence / Magic.
- **Skills** grouped by category, with specializations.
- **Karma** — current balance + lifetime earned.
- **Nuyen** — current + recent transactions log.
- **Reputation** — per-faction standing + threshold label.
- **Contacts** — list with Connection / Loyalty / last contact.
- **Cyberware** — installed list with Essence cost + tooltip.
- **Magic** (if Awakened) — spells known, spirits bonded / services owed, drain history.
- **Addiction / health** — current addiction tiers, withdrawal state, ongoing debuffs.

## Map

- **Per-district local map** — isometric overview of current district with zoom. Fast-travel between discovered venues (time-cost advance per distance).
- **Mini-map** — HUD compass showing current scene's navigable area.
- **Post-MVP:** full Seattle metroplex overview map once multiple districts open.

## Journal

- **Active run** — brief, objectives, complications, known map, contacts met.
- **Completed runs** — history log.
- **Contacts** — who's met, voice quote, services.
- **Places** — discovered venues with ambient notes.
- **Rumors** — overheard gossip flagged for later follow-up.
- **Achievements / trophies:** out of scope at MVP.

## Tutorial

- **No dedicated tutorial level.** The MVP run doubles as first experience.
- **Contextual tooltips** on first encounter: first combat, first Matrix jack-in, first spellcast, first dialogue check, first shop, first sex scene, first drug use, first addiction tick.
- Tooltips dismissable; re-openable from a "Help" section in the commlink.

## Accessibility (MVP)

- **Subtitle customization.** Size, background opacity, speaker-label on/off.
- **Text scale** and **dyslexia-friendly font** option across all UI text.

Post-MVP accessibility expansions:

- Colorblind modes.
- Motion reduction (camera shake / flashing / particles).
- Combat auto-resolve for non-combat-focused players.
- Full input remapping (already MVP-planned for keyboard; controller support is post-MVP).

## NSFW UI reactivity

- **Per-scene skip** button for NSFW scenes (no full-game toggle).
- **Content-tag indicator** at scene start — not a gate, just context.
- **Romance visit scheduler** inside the commlink (Messages → scheduled visit invites from the romance contact).

## Input / keybinds

- **Mouse + keyboard** primary at MVP.
- Default binds: `Tab` = commlink hub, `C` = character sheet, `M` = map, `I` = inventory, `J` = journal, `N` = notifications, `Esc` = options, `Space` = confirm / cancel combat pending.
- **Rebindable.**
- Controller support: **out of MVP**, planned post-MVP.

## MVP deliverables

- Diegetic-cyber HUD art for the core panels (commlink, combat, Matrix, inventory, character sheet, dialogue).
- At least one scene-tonal UI variant to prove the system (e.g. Matrix green-wireframe theme).
- Mouse-keyboard binding set with rebind support.
- Contextual tooltip system with content for ~15 trigger events.

## Open questions

- Controller support post-MVP timing.
- Cross-resolution scaling — how dense on 4K, how playable at 1080p.
- Stream-safe / content-warning pre-launch screen — probably skipped for personal project.
- Live "ARO flicker" VFX on HUD — atmospheric or distracting?
- UI localization plumbing — hooks in place at MVP even if shipped English-only.
- Commlink-as-scene-intrusion — does an incoming contact call interrupt gameplay, or queue silently?
