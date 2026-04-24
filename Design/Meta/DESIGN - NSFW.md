# DESIGN - NSFW

## Decision

**DECIDED:** Adult content is a **first-class design pillar**, co-equal with combat, Matrix, magic. Not optional flavor, not toggleable — always-on, illustrated-explicit register where scenes call for it. The project is personal; there is no commercial audience to filter for.

## In-scope content

All of the following are first-class design targets:

- **Sex, romance, sex work.** Romance arcs with contacts; brothels, escorts, clients, and sex-work runs as venue types and run types. On-screen sex scenes.
- **BTL chip content** (including adult chips). BTL economy, content pipeline, addiction, and chip-farming setups. Adult-simsense studios as venues.
- **Drug / addiction systems.** Novacoke, Cram, Kamikaze, BTL addiction, withdrawal, tolerance, dealer economies, overdose. Mechanical simulation, not just flavor.
- **Graphic violence, torture, wetwork, body horror.** Cyberzombies, ghouls, blood magic, ritual sacrifice, Night-of-Rage aftermath content, insect spirit themes. On-screen and illustrated.
- **Political extremism as faction content.** Humanis Policlub, KKK, The Order, Alamos 20,000 etc. as antagonist factions with runnable content. Hate-crime events as part of the simulation.
- **The broader SR dark register.** Organleggers, meta-human discrimination, corporate wage-slavery, privatized police brutality, extraterritoriality abuses, magical atrocities.

## Register

**Illustrated-explicit.** Explicit written descriptions *and* on-screen illustrations for sex and graphic scenes. Register selected per scene — a sex scene between contacts should read and look different from a BTL-studio industrial-chip shoot, which should look different from wetwork.

- **Text:** explicit, unhedged, character-true. Not leering; not coy. Adult literacy.
- **Art:** illustrated (hand-authored or diffusion-drafted then curated). See Narrative/DESIGN - Writing.md and Technology/DESIGN - AI Tooling.md for the dev-time pipeline.
- **Animation:** out of MVP scope. Static illustrated scenes are acceptable; 3D sex animation is post-MVP at earliest (likely never).

## Toggle

**Always-on. No toggle, no settings unlock, no content warnings as a gate.** The game is the game. If NSFW is off-putting, this is not the game for that audience.

- A per-scene "skip" option is acceptable UX (player can skip a specific scene they are not in the mood for), but NSFW is not a global toggle.
- Accessibility: subtitle / text-alt for all art. No hiding of the text layer.

## Canonical register anchors

To keep NSFW content specific rather than generic, each dark-register slot has a **canonical anchor faction** whose flavor defines the project's register for that kind of content. Other factions operating in the same register get distinct cultural / methodological character to avoid faction-flattening.

- **Corporate torture + mind-altering drug coercion:** anchor = **Mitsuhama Computer Technologies** (per SR1E Seattle Sourcebook p.22 canonical flavor). Mitsuhama's intel-division torture sites are the project's template for corp-tier torture content (on-screen where scene-tagged; scene-skip UX available). Other corps developing similar content get distinct registers (e.g. Aztechnology magical-ritual-based, Renraku deep-Matrix-based — TBD as those corps ingest).
- **Hate-crime / racial violence:** anchor = **Humanis Policlub** (per SR1E Seattle Sourcebook pp.17–18). Night-of-Rage-style mass incidents + Liberty-Village-style firebombings are the project's template for organized-bigotry content.
- **Extreme magical / demonic register:** anchor TBD (likely the blood-magic / ritual-circle underworld once those pages ingest).
- **Sex-work upmarket register:** anchor = **licensed pleasure houses** (Lord of Out-Style / Lucy's / Bedlight per p.13). Legal, medically-inspected, expensive — the project's top-tier sex-work register. Street-level and exploitative sex-work registers distinct and authored per canonical source as those arrive.
- **BTL + drug addiction register:** anchored in the simulated-addiction system (see `Character/DESIGN - Downtime.md` + `World/DESIGN - Economy.md`).

The deep-NPC rule (see `Narrative/DESIGN - Writing.md`) applies within every register: Mitsuhama torturers are specific people with specific reasons, not stock villain clichés; Humanis rank-and-file have human motives; pleasure-house performers have lives beyond the job.

## Hard floor (project-independent)

Absolute limits I (the assistant helping build this) will not cross regardless of NSFW-unlock status:

- **No sexual content involving minors** in any form. Characters in sexual contexts are adults.
- Everything else in the SR dark register is open for design discussion.

## Pipeline

- **Authoring:** human drafts or dev-time LLM drafts (see `Technology/DESIGN - AI Tooling.md`). Every shipped line is human-reviewed.
- **Illustration:** dev-time diffusion-tool drafts, human-curated and edited. No runtime generation. Shipped art is static.
- **Storage:** NSFW scripts live in `Data/Content/Scenes/` alongside non-NSFW scenes (no separate-folder ghetto — scenes are tagged).
- **Tagging:** each scene declares `nsfw_kind:` (`sex`, `violence`, `drug`, `horror`, `mixed`) and `intensity:` (`suggestive`, `explicit`, `extreme`) for the scene-skip UX, not for gating.

## Integration with systems

- **Economy:** sex work, BTL chip sales, drug sales are real income sources. Rent can be paid with nuyen from any of them.
- **Reputation:** some social circles react to your documented behavior (sex work, violence, addiction). Tracked, not judged — reputations open and close doors.
- **Contacts:** can become romantic/sexual. Multiple simultaneous relationships allowed; consequences tracked. No monogamy assumption.
- **Health:** drug addiction and STI-equivalents (HMHVV, cyber-sexual-transmitted infections) are mechanical if we choose to simulate — TBD per system-specific pass.
- **BTL:** chip content is playable content — you can record, sell, and consume chips. Running a chip studio is a possible career path.

## MVP scope

At MVP, the NSFW pipeline must:

- Ship at least one **illustrated-explicit** scene in the vertical slice. Art at MVP: **diffusion-drafted stills, human-curated, shipped as-is** (no hand-paint pass required). Full animated sex scenes are a stated post-MVP goal.
- **One romance-eligible named contact** authored with full romance path (dialogue milestones + explicit scene). Validates the romance-scene pipeline.
- **Addiction mechanics** implemented for drugs and BTL chips (tolerance, addiction risk, withdrawal). Simulated, not narrative-only.
- **BTL chips as consumable items** working end-to-end: buy, consume, effect (short buff/debuff), addiction hook, sell. A small chip-library authored.
- Scene-tagging and per-scene-skip UX working (no global NSFW toggle).
- Prove the authoring → diffusion → curate → ship loop end-to-end.

Post-MVP goals (tracked, not MVP-blocking):

- Full animated sex scenes (from static illustrations to animation).
- Additional romance-eligible contacts (multiple simultaneous allowed; consequences tracked).
- Brothel hubs as walkable venues.
- BTL-studio run types (production, extraction, sabotage, sabotage-of-rival-studio).
- Full BTL career path (record / sell chips as a mini-profession).
- Sex-work side hustle as a real income loop.
- Expanded drug catalogue and deeper addiction-system content (detox clinics, withdrawal-driven runs).

## Open questions

- How explicit does MVP art get? Shipping art vs placeholder (to validate the pipeline only)?
- STI / health mechanics — simulated or narrative-only?
- Romance mechanics — classic CRPG "approval" meter, or looser simulation?
- Consent modeling in systems — is consent tracked mechanically, or narrative-only?
- BTL chip content as a mini-game (authoring / recording) vs. just as inventory items?
