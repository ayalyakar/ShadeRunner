# DESIGN - Reputation

## Decision

**DECIDED:** **Per-faction numeric reputation** at MVP. No separate street-cred axis; no per-district axis. A single rep number per faction, integer in range roughly `[-100, +100]`, modifies dialogue availability, shop access, patrol response, contact introductions, and some run availability.

## Model

### Data shape

Each faction carries a `standing:` field in `Data/Lore/Factions/<faction>.yaml`:

```yaml
standing_default: 0             # neutral on new-game
thresholds:
  hostile: -60                  # attack on sight / refuse service
  unfriendly: -20               # cold dialogue; jacked prices
  neutral: 0
  friendly: +20                 # discounts; warm dialogue; introductions
  trusted: +60                  # inner-circle content; special runs
```

### Per-save state

Saved game stores current standing per faction — simple key/value. Initial standing comes from defaults plus chargen-background adjustments (lifepath-lite may grant a contact and a small starting standing).

## Events that move rep

- **Run completion.** Delivering on a Johnson's run moves that Johnson's faction standing up. Betraying / double-crossing moves it down sharply.
- **Collateral.** Killing a faction's members during a run moves that faction's standing down — even if the run was for a different party.
- **Public action.** Rally attendance, venue patronage, publicized violence — scripted rep deltas.
- **Contact-specific favors.** Favors owed / called-in move the contact's faction standing.
- **Dialogue choices.** Some lines carry explicit rep deltas.

## Effects by threshold

### Dialogue
- Thresholds gate conversational branches. Hostile factions' NPCs refuse to talk; friendly factions open inner-circle lines.

### Shops & services
- **Hostile:** refuse service or massively upcharge (200%+).
- **Unfriendly:** upcharged (130–150%) or restricted stock.
- **Neutral:** standard.
- **Friendly:** discount (90%) and wider stock.
- **Trusted:** deep discount (75%), rare stock, custom orders.

### Patrol / enforcement
- Hostile to Lone Star / Humanis / etc. → more stop-and-frisks, shorter response times against the PC, more aggressive arrest tactics.
- Friendly (e.g. to a Yakuza Ring in their turf) → fewer harassments, escorted entries, occasional tip-offs.

### Contact introduction
- Friendly factions' named NPCs can introduce the PC to other contacts inside their faction. Trusted factions unlock deeper-tier contacts.

### Run availability
- Some runs require minimum standing with a faction (can't get a Mafia wetwork job if Mafia thinks you're a cop).
- Some runs destroy standing with the target faction by definition (a Johnson may front for a rival faction — accepting means locking in the enemy).

## NSFW-aware rep

Several rep axes are NSFW-relevant:

- **Sex-work reputation.** Standing with sex-work circles (fixers / madams / BTL-studio operators) gates access to that economy's best contacts and jobs. PCs who work sex-side can climb this rep.
- **BTL-community rep.** Chip-dealer and BTL-consumer circles react to the PC's documented BTL behavior.
- **Addict rep.** NPCs in addiction-adjacent communities note the PC's visible drug / chip status. Some contacts respect it (user solidarity), some weaponize it (blackmail, manipulation).

These are modeled as regular faction rep — the relevant "factions" are simply the social circles (`Data/Lore/Factions/<sex-work-circle>.yaml` etc.).

## Ambient effects (MVP — shallow)

- Dialogue barks from random NPCs reference rep ("heard you did a number on the Crush last week").
- Shop greeter text changes per threshold.
- Lone Star patrol frequency and aggression in the PC's current district adjusts per Lone Star standing (scripted, not simulated).

## Post-MVP expansion

- **Street cred** (separate axis). General "runner" rep independent of faction politics. Gates access to high-tier fixers and bleeding-edge runs.
- **Per-district standing.** The PC can be beloved in Redmond and reviled in Downtown. Requires district-scale per-NPC flag system.
- **Named-NPC standing** separate from faction standing (you can be trusted by a specific Yakuza lieutenant while hostile to the Ring overall).
- **Public-infamy thermometer** with ambient news reactivity.

## Open questions

- Rep numeric granularity — is `+20` hit in one run or is it a slow climb of 10 smaller deltas?
- Rep decay over time (friendships go cold if neglected) — MVP or post-MVP?
- How does the UI expose rep? Full numeric, textual label only (Hostile / Neutral / Friendly), or both?
- Does rep ever "lock" (trusted status that can't be undone by one bad run)?
- Faction-of-factions (Yakuza as an umbrella with Rings inside) — one rep or per-Ring?
