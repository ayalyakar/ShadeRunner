# DESIGN - Lifestyle

## Decision

**DECIDED:** Lifestyle is a **monthly-rent tier** tracked explicitly. PC starts at **Low** (2,000¥/month). Missing rent **demotes one tier immediately** and fires a consequence event (eviction, contact loss, reputation hit). Squatter is the rent-free floor; Street is the SINless-outdoors fallback.

## Tiers

| Tier | Monthly rent | Description | SIN requirement |
|---|---|---|---|
| **Street** | 0¥ | No permanent shelter. Sleeps in doorways / abandoned buildings. | SINless OK |
| **Squatter** | 500¥ | Abandoned apartment, illegal hook-ups, no legal address. | SINless OK |
| **Low** | 2,000¥ | Small apartment, spotty utilities, ganger-adjacent neighborhood. **MVP default.** | Fake SIN 1+ |
| **Middle** | 5,000¥ | Functional neighborhood, working utilities, commlink subscription. | Fake SIN 3+ or real |
| **High** | 10,000¥ | Safe, clean, amenities. | Real SIN or fake SIN 5+ |
| **Luxury** | 100,000¥ | Downtown penthouse. Unreachable at MVP. | Real SIN + corp affiliation |

Each tier includes food, utilities, commlink subscription baseline.

## Per-tier effects

### Street
- No rent; no address; no SIN-required services.
- **Health drain:** slow ongoing Stun damage (exposure, food insecurity).
- **Gear security:** zero — carried items can be stolen during night / unconsciousness.
- **Contacts penalty:** Loyalty-raise decay faster; some contacts refuse Street-tier PCs.
- **Heal rate reduced** (no safe rest).

### Squatter
- No rent.
- Basic shelter; gear stays put when the PC sleeps there.
- Utilities unreliable — occasional no-power / no-water events.
- **Healing:** slower than higher tiers.

### Low (MVP default)
- Rent 2,000¥/month.
- Functional utilities.
- Standard healing rate.
- Neighbor NPCs — ambient texture, occasional hook events.
- Can host contacts / romance visits.

### Middle
- Rent 5,000¥/month.
- +1 Willpower-equivalent bonus for a daily "rested" buff (real sleep, clean space).
- Unlocks housing-specific upgrades (purchased commlink line, home-security system).

### High
- Rent 10,000¥/month.
- Corporate / wealthy-tier reactivity — corp Johnsons take the PC more seriously.
- Unlocks home-office / home-lodge upgrades (mage lodge at home, decker sanctum).

### Luxury
- Rent 100,000¥/month.
- Socially significant — invited to corp galas, Downtown events, Trid-celebrity circles.
- Unreachable at MVP.

## Rent cycle

- **Billing date:** 1st of each in-game month.
- **Grace period:** zero at MVP (immediate downgrade on failure). Post-MVP option: 3-day warning events.
- **Payment:** automatic from nuyen balance if funds exist. PC can opt into "don't auto-pay" per tier — but then a manual-pay event is triggered on the 1st.
- **Paying ahead:** allowed. Pay multiple months up front if the PC has cash.

## Consequences of failure

On missed rent, the lifestyle tier drops **one step**. Consequences fire as scripted events:

| Previous tier | Drops to | Consequence events |
|---|---|---|
| Low | Squatter | Eviction scene; landlord keeps some deposit gear; one named contact's Loyalty -1 ("heard you got evicted, kid"); one scripted move-in scene at the Squatter location. |
| Middle | Low | Eviction scene (corp landlord less sympathetic); commlink subscription interrupted briefly. |
| High | Middle | Corp patronage dropped; related Johnson's Loyalty -1. |
| Squatter | Street | Squatter squat raided / burnt / repossessed. Possession loss (roll for what's still carried). SINless-default flag set if PC's fake SIN was tied to the squat's address. |
| Street | Street | Stays. Ongoing Stun damage continues. |

## Upgrading tier

- Moving up requires **paying the new tier's first month** plus a **one-time deposit** (typically 2× monthly rent).
- Finding the new place is a Downtime action; can take a few in-game days to close.
- Some tiers require SIN tier (Middle needs fake SIN 3+, High needs real / fake 5+).

## Home location

- Each tier has a default neighborhood. At MVP, PC's Low-tier apartment is in the hand-built Redmond MVP neighborhood (exact spot TBD when Redmond ingests).
- Post-MVP: players can choose neighborhood within tier; different neighborhoods give different ambient flavor, different contacts-in-range, different heat levels.

## Home as venue

- PC can invite contacts over (romance visits, fixer meetings, low-key conversations).
- PC can store gear (inventory isn't carried entirely).
- PC can sleep → time advance + healing.
- Home has a small **home-upgrades** catalogue: bed (better rest), basic decker rig / magic lodge (tier-gated), wall-safe, surveillance system, illegal utility hook (cuts rent slightly).

## NSFW lifestyle crossover

- Higher-tier lifestyle unlocks better romance-visit scenes (e.g. a Low-tier apartment is functional; Middle-tier adds a decent bedroom; romance-scene variants reactive to tier).
- Brothel-adjacent PC career path (post-MVP) may allow **"working from home"** (running a small independent sex-work operation from the apartment) — affects neighbor / contact reactions.
- BTL-addict PC with missed rent — specific Squatter event emphasizes the addiction-poverty loop.

## MVP scope

- **Tiers implemented:** Street, Squatter, Low, Middle. High / Luxury authored as lore only.
- **PC start:** Low.
- **Rent cycle:** one payment event in the vertical slice (clock permitting).
- **Failure path:** if rent missed during vertical slice, the Low → Squatter drop fires with its consequence scene — validates the failure loop.
- **Home-upgrades catalogue:** minimal at MVP (a bed, a safe, one illegal utility hook). Rest post-MVP.

## Open questions

- Rent-automation UX — silent auto-pay or notify?
- Home-upgrades progression pace.
- Neighborhood choice within tier at MVP — scope creep risk.
- Squatter-to-Low upgrade gating — just nuyen, or narrative beat?
- Can the PC voluntarily downgrade? (e.g., drop to Squatter to save cash during a lean run streak.)
- "Haunted" / story-cursed residences — are certain apartments content-rich (previous tenant's plot hook)?
