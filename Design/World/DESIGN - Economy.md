# DESIGN - Economy

## Decision

**DECIDED:** Multi-layer SR-classic economy combining **SIN-tier banking**, **black market & barter**, **itemized lifestyle bills**, **monthly rent** pressure, **run-payout-driven nuyen inflow**, and **parallel NSFW / drug / BTL income channels**. Jobs, gear, and daily needs all plug into a shared price/availability model.

## Currency

- **Nuyen (¥).** Primary currency. Digital credstick balance + paper cash (lower security, higher anonymity).
- **Favors.** Tracked as currency-equivalent against contacts. Not yen-convertible; spent against specific contact services.
- **Karma.** Experience. Separate ledger. Not money. See `Character/DESIGN - Progression.md` (future).

## Price and availability

Per item:
- **Baseline price** by edition / era (MVP uses SR1E calibration).
- **SIN tier required** to buy legally.
- **Availability rating** (classic SR: higher availability = harder to source, longer wait).
- **Black-market markup** curve scaling with heat and district.

Per district:
- Local price multiplier (Redmond lower than Downtown).
- Shop inventories refresh on a weekly cadence at MVP.

## Calibration anchor

- **Redmond per-capita income: 6,000¥/year (~500¥/month)** — the Barrens baseline, carried forward from SR1E canon.
- Lifestyle tier pricing calibrated such that a working runner at **Low tier (2,000¥/month)** pays ~4× Redmond median monthly income — matches the SR-intended precarity.
- Run payouts scale against this anchor so one successful mid-tier run covers 1–3 months of Low lifestyle.

## SIN economy

- PC can hold multiple SINs: real SIN (if any) + fake SINs of rating 1–6.
- Higher-rating fakes survive more SIN-checks; cost more to forge; degrade on failed checks.
- SIN-check events: licensed stores, border crossings, legal employment, hospital visits, airport, corp zones.
- **SINless** characters survive via black market, barter, contact networks; cannot legally rent (squatter-tier only), cannot shop in corp stores, cannot use most public systems.

## Lifestyle tiers (MVP)

| Tier | Monthly rent | Description |
|---|---|---|
| Street (SINless default) | 0 | No roof. Real SR precarity. |
| Squatter | 500¥ | Abandoned apartment, illegal hook-ups. |
| Low | 2,000¥ | Small apartment, spotty utilities. **MVP default PC tier.** |
| Middle | 5,000¥ | Decent neighborhood; functional everything. |
| High | 10,000¥ | Safe, clean; amenities. |
| Luxury | 100,000¥ | Downtown penthouse tier. Post-MVP in practice. |

Lifestyle includes food, utilities, commlink subscription baseline. Line-item granularity available if player opts in (cancel fixer retainer to save 200¥/mo, etc.).

## Run payout economy

Payouts scale with:
- **Target tier:** street < gang < mid-corp < AA < AAA.
- **Complexity:** more rooms / guards / systems / hostages.
- **Heat:** higher risk → higher pay.
- **Time pressure:** rush jobs pay more.
- **PC reputation / fixer Connection:** better contacts = better cuts.

MVP retrieval run target payout: **~3,000–6,000¥ per runner** — covers 1.5–3 months of Low lifestyle with modest surplus for gear / training.

## Income channels (parallel to runs)

All are first-class at MVP:

- **Runs** (primary).
- **Sex work.** Per-session street rate; higher rates at brothels / escort gigs / club work. Entry-tier work modest (~50–200¥/session); higher-tier (~1,000–5,000¥/session) requires rep and contacts.
- **BTL chip sale.** PC can fence chips recovered from runs or (post-MVP) record their own.
- **Drug sale.** Street-corner dealing; Novacoke / Cram / Kamikaze / BTL flip. Mid-risk; low-margin per unit.
- **Loot fencing.** Gear / data pulled from runs sold at 20–50% of MSRP via fixer or fence contact.
- **Contact favors.** Paid-cash favor returns from specific contact relationships.

## Expenses

- **Rent** (monthly, per tier).
- **Food / utilities** (rolled into lifestyle; itemizable).
- **Gear purchase** (ad-hoc).
- **Cyberware installation** (street doc fees + nuyen cost).
- **Medical** (street doc visit, stabilize, Trauma Patch).
- **Drug / BTL habits** (ongoing cost if addicted — mechanical, not just flavor).
- **Fixer retainer** (optional monthly 100–500¥ for faster job flow).
- **Commlink subscription** (rolled into lifestyle baseline).
- **Bribes** (case-by-case).

## Canonical illicit sub-economies (per district)

Per-district data files declare **canonical illicit sub-economies**. Each declares MVP presence (ambient / MVP run-content / post-MVP). Reference canon (when Redmond is ingested) will likely land:

- **BTL chip trade.**
- **Body-parts trade** (organlegger economy).
- **Inferior industrial products** (Redmond Toxic Castle fraud pipeline).
- **Arson-for-hire** (mundane + fire-spirit summoning).
- **Black-magic / hexed-reagent market.**
- **Sex-work economy** (brothels, escorts, BTL-studio performers).
- **Drug trade** (Novacoke / Cram / Kamikaze / BTL addiction substrates).

These are content layers on top of the standard price / availability / SIN model, not replacements.

## NSFW-aware economy

- Sex-work, BTL sale, drug dealing are **real income sources** — rent can be paid entirely from any of them.
- Addiction is a **real ongoing expense** — BTL-addicted PCs lose nuyen and Essence to the habit.
- Brothel / BTL / drug venues are shops with full price models.

## MVP scope

- Lifestyle at Low tier (default PC start).
- One run payout (the MVP retrieval).
- Shop inventories at minimum:
  - One street-doc shop (cyberware / healing).
  - One fixer shop (gear / contacts).
  - One fence (loot / BTL chips).
  - One street dealer (drugs).
  - One NSFW venue (brothel or BTL studio) with purchasable services.
- SIN-check: at least one scripted scene that checks PC SIN rating.
- Rent event: one monthly rent payment on the vertical slice clock.

## Open questions

- Inflation across era drift (2050 → 2064). Same yen? Explicit curve?
- Corp scrip / alternative currencies — MVP or post-MVP?
- Taxation / laundering — simulate for the runner lifestyle?
- Court costs, fines, bribes — structured or narrative-only?
- BTL sub-economy pricing — per-chip table or narrative?
- Sex-work pricing tiers — MVP gradient or post-MVP expansion?
- Drug pricing elasticity — static or district-dependent?
