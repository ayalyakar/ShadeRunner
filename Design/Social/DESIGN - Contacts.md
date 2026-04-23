# DESIGN - Contacts

## Decision

**DECIDED:** Contacts are **named, persistent NPCs** with a Connection rating, relationship standing, voice profile, venue, and service portfolio. The PC builds a contact network over time; contacts are consumed (favors spent), nurtured (trust built), burned (betrayed), and romanced. Some contacts are MVP-scope; many are post-MVP.

## Contact shape

Every named contact lives in `Data/Lore/NPCs/<name>.yaml` and carries:

```yaml
contact_profile:
  connection: 3                    # 1-6; breadth of their network
  loyalty_default: 2               # 1-6; trust / willingness, default at first meet
  venue: "Data/Lore/Places/Bars/Velvet Edge.yaml"
  services:
    - type: "fixer"                # job leads
      availability: "weekday evenings"
    - type: "fence"
      markup: 1.3                  # sells at 130%, buys at 40% of MSRP
  voice:
    engine: xtts
    model_ref: "voices/fixer-seasoned-redmond.safetensors"
  relationship:
    romance_eligible: true
    default_orientation_flexible: true   # willing to romance any PC metatype/gender at MVP
  faction_affiliation:
    primary: "Independent"
    secondary: ["Redmond local syndicate"]
```

### Connection (1-6)
- The **breadth** of their network. How many doors they open.
- 1 = a single niche contact; 6 = a corp-tier facilitator.
- MVP fixer is Connection 3–4.

### Loyalty (1-6)
- The **depth** of their commitment. How much risk they'll take for the PC.
- Loyalty grows with shared runs, favors repaid, time invested.
- Loyalty drops with betrayal, ignored favors, violence against the contact's circle.

### Services
- Each contact offers a portfolio. Common types:
  - **Fixer** — run leads.
  - **Fence** — sell loot / BTL chips.
  - **Street doc** — cyberware / healing.
  - **Armorer** — gear purchase.
  - **Talismonger** — magical supplies.
  - **Decker / Matrix support** — Matrix help.
  - **Information broker** — intel.
  - **Safehouse operator** — shelter for heat.
  - **Madam / BTL producer** — NSFW-adjacent services and intel.
  - **Bartender / confidant** — social services (drinks, ears, news).

### Voice profile
- Every named contact has a distinct voice (see `Presentation/DESIGN - Audio.md`).
- Voice stays consistent across all their lines — hand-authored and templated.

## MVP contact roster

At minimum MVP, a handful of named contacts:

| Contact | Archetype | Connection | Loyalty default | Romance? | Notes |
|---|---|---|---|---|---|
| **Fixer (name TBD)** | Seasoned Redmond fixer | 3–4 | 2 | no (MVP) | Introduces Johnson; recurring job source. Warm, gruff. |
| **Corporate Mr. Johnson** | Corp fixer | 4 | 1 | no | The MVP run's client. Single-scene + payout at MVP. |
| **Fellow runner (romance)** | Freelance runner | 2 | 2 | **yes** | Met on the MVP run. Romance arc shipped in vertical slice. |
| **Street doc** | Illegal cyberclinic | 2 | 2 | no (MVP) | Cyberware + healing services. |
| **Fence** | Barrens fence | 2 | 1 | no | Sells loot + BTL chips. |
| **Bartender** | PC's regular bar | 2 | 3 | no (MVP) | News, gossip, low-stakes tip-offs. |
| **Madam / BTL producer** | Brothel / BTL studio operator | 2–3 | 1 | no (MVP) | NSFW venue lead; sex-work and BTL-job intel. |
| **Street dealer** | Drugs | 1 | 1 | no | Novacoke / Cram / Kamikaze supplier. |

**Total MVP contacts: 7–8 named NPCs.** Each has a voice, a portrait, a venue, a service portfolio, and enough dialogue to support the MVP-run vertical slice plus a few downtime visits.

## Contact interaction

### Calling / visiting
- Call a contact (commlink) for intel or to request a service; physical visit for deeper interactions.
- Venue matters — a contact at a bar is easier to approach than one at a corp office.
- Time matters (see `World/DESIGN - Time.md`) — contacts follow schedules.

### Favors
- Contacts can **owe** the PC or be **owed**. Tracked explicitly.
- Calling in a favor has a loyalty cost but opens content (free service, dangerous ask).
- Refusing a contact's favor request drops loyalty.

### Trust-milestone scenes
- At loyalty thresholds (3 / 4 / 5 / 6), a named contact unlocks a **trust scene** — a scripted dialogue beat that deepens the relationship, often including a rep reward or a new service.
- Romance-eligible contacts have romance-specific scenes interleaved.

## Romance

### Model
- **Any romance-eligible contact** (flagged `romance_eligible: true` in their profile) can enter a romance arc with the PC.
- **No approval meter per se**; loyalty + dialogue choices unlock romance beats.
- **Multiple simultaneous romances allowed** — see `Meta/DESIGN - NSFW.md`. Other contacts may react, jealousy is modeled in post-MVP.
- **Orientation:** at MVP, romance-eligible contacts are flexible for any PC metatype / gender / appearance. Post-MVP can add orientation-specific reactivity.

### Romance arc beats (MVP: one full arc)
1. **Meet** — first encounter (on the MVP run, for the designated romance contact).
2. **Rapport** — 2–3 downtime / shared-scene interactions that raise loyalty above friendship threshold.
3. **First intimate scene** — illustrated-explicit scene tagged `nsfw_kind: sex`, shipped with art + XTTS / ElevenLabs dialogue.
4. **Relationship** — ongoing dialogue reactivity; contact available for scheduled downtime visits.
5. *(Post-MVP)* Long-term arc — conflict, resolution, commitment / breakup / open-relationship branching.

### NSFW scene structure
- Text-first: the scene's dialogue and narration are the authoritative source.
- Illustrated stills punctuate key beats (arrival, escalation, climax, aftermath).
- Player agency: choice points during the scene (what to do / how to respond).
- Consequence: scene outcomes affect loyalty, may unlock later beats, may fork the arc.

## Burning / losing contacts

- **Betrayal** (visibly screwing them over on a run, selling them to a rival, killing their people) drops loyalty to 0 and flips them to **hostile**. Hostile contacts refuse service and may retaliate.
- **Neglect** (ignoring favors, not visiting, letting calls go) decays loyalty over in-game weeks.
- **Burning a contact** (deliberate break) is sometimes the right move for a run — a Johnson may want the PC to use and discard a specific contact. Explicit dialogue choice.

## Post-MVP expansion

- **Connections 4–6 tier contacts** — corp-level Mr./Ms. Johnson, AAA fixers, legendary street doc, master talismonger.
- **Contact-introduces-contact** pipeline — loyalty-gated network growth.
- **Contact rivalries** — two contacts can feud; supporting one drops loyalty with the other.
- **Multiple romance arcs** — romance multiple contacts simultaneously with reactivity / jealousy.
- **Extended romance content** — marriage / commitment / moving-in / polyamory modeling.
- **Contact gear specialists** — each contact carries unique stock.

## Open questions

- Contact portrait consistency — same character seed across all their appearances.
- Loyalty decay timescale — what's "neglect" quantitatively?
- Can the PC meet a contact while currently hostile to their faction (e.g. fence who works with Mafia while PC is Mafia-hostile)?
- Romance gating on loyalty threshold vs. narrative beats — hybrid how?
- NSFW scene authoring — per-romance handwritten, or templated with variables?
- Romance with faction NPCs (e.g. a Yakuza lieutenant) — loyalty vs. faction rep crossover rules.
- Named-contact death during a run — permadeath or revivable?
