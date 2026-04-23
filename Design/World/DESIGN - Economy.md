# DESIGN - Economy

## Decision

**DECIDED:** A multi-layer economy that combines **SIN-tier banking**, **black market & barter**, **detailed itemized bills**, and **monthly lifestyle payments** (SR classic). Jobs, gear, and daily needs all plug into the same price/availability model.

## Price and availability

Per item:
- **Baseline price** by edition / era (hybrid calibration).
- **SIN tier required** to buy legally.
- **Availability** (SR-standard rating: how hard to find).
- **Black-market markup** curve relative to heat and district.

Per district:
- Local multipliers and seasonal/event-driven shifts (e.g. after a turf war, prices shift).
- Item inventories at shops/fixers refresh on a cadence.

## Calibration anchor

- **Redmond per-capita income: 6,000¥/year (≈ 500¥/month)** is the anchor point for lifestyle tier pricing and run-payout curves across the game. Source: `Data/Lore/Districts/Redmond.yaml` (SR1E, p. 127).
- Lifestyle tiers are calibrated against this anchor so that a working Barrens runner at Low tier (2,000¥/month) pays ~4× median Redmond monthly income — matching the precarious framing SR intends.
- Other districts' income data (when transcribed) provide relative multipliers against this baseline.
- **Era inflation is an open question.** Same yen across decades is the current default; an explicit era-scaling curve may be added later.

## SIN economy

- PC can hold multiple SINs at varying legitimacy tiers (real, fake-Rating-1 through fake-Rating-6).
- Higher-tier SINs: more stores, legal employment, licensed gear.
- Lower-tier or SINless: black market, barter, fixer-only sales.
- SIN-check events: border crossings, specific stores, legal jobs, hospital visits.

## Job economy (see `Narrative/DESIGN - Structure.md` for framing)

Jobs arrive via four channels, all simulated:
1. **Johnson meets / fixer calls** (classic SR framing).
2. **Shadowland BBS / job boards** (post-Matrix era evolves these).
3. **Emergent opportunities** (overheard, stumbled into).
4. **Long cons / self-directed heists** (player identifies target).

Payouts scale with:
- Target tier (AAA > AA > mid corp > gang > street).
- Run complexity, heat, time pressure.
- Player's reputation and Connection of the fixer.

## Lifestyle payments

- Monthly **rent** tied to a lifestyle tier (Squatter → Luxury).
- **Food, utilities, commlink subscriptions, fixer retainers** as separate line items if the player wants granularity.
- Missing payments causes lifestyle downgrade and concrete consequences (eviction, utility cut, commlink cut, contacts lost).

## Barter & favor economy

- Fixers and contacts often prefer favors over money.
- Barter lets a SINless runner operate without banking.
- Favor debts are tracked explicitly; calling in debts is a core social-system mechanic.

## Open questions

- Inflation across decades — explicit, or invisible rebasing?
- Corp scrip / alternative currencies.
- Taxation and laundering — how much to simulate for a non-hero player?
- Insurance, legal fines, court costs — edge cases but canonical.
