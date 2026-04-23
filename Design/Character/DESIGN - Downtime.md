# DESIGN - Downtime

## Decision

**DECIDED:** Downtime is the in-between-runs phase where the PC **spends karma, manages contacts, shops, trains, maintains lifestyle, and consumes NSFW / drug / BTL content**. All downtime actions **advance the real-clock time** (see `World/DESIGN - Time.md`) and can compound into full-day blocks.

## Downtime actions (MVP)

### Self-improvement
- **Train skill** — burn karma + time to raise a skill. 4–8 hours at a gym / range / library per raise; karma cost per the progression table.
- **Train attribute** — longer time block (8+ hours over several in-game days) + karma.
- **Learn new spell / program / adept power** — requires teacher / library / lodge + downtime hours + karma.
- **Meditation** — mages can meditate for magical recovery, astral perception practice (post-MVP full astral).

### Contact maintenance
- **Call a contact** — short time; gains ambient info; small Loyalty tick if overdue.
- **Visit a contact** — longer time; unlocks dialogue; can raise Loyalty via trust-scene beats.
- **Buy a drink for a contact** — social gesture; small Loyalty tick; nuyen cost.
- **Favor exchange** — spend a favor owed or offer one. Tracked in contact state.

### Economy
- **Shop** — browse fixer / street doc / fence / dealer inventories. Time per visit.
- **Sell loot** — fence interaction.
- **Pay rent** — automatic on 1st, but can pre-pay.
- **Heal** — visit street doc. Time + nuyen; heals Physical / Stun tracks beyond the PC's self-heal rate.

### Sleep / rest
- **Sleep** — 6–10 hours. Time advances; Stun heals; Physical heal continues at rest rate.
- **Long rest** — 8+ hours at Low lifestyle or better. Full Stun recovery; daily-buff refresh.
- **Rough rest** — less than 4 hours or at Street tier. No recovery; may impose fatigue debuff.

### Sex-work / NSFW side hustle (MVP-light)
- **Work the corner / club / brothel** — sex-work session. Small nuyen earn; time cost; low rep with sex-work circle; SIN-dependent reactivity. Brothel work pays more but requires venue access / contact.
- **Consume BTL chip** — short time (session-length on chip); stat effect (buff/debuff); addiction tick.
- **Use drugs** — short time; stat effect; addiction tick.

### Romance
- **Romance visit** — visit the romance contact's venue / apartment; available at specific Loyalty thresholds. Unlocks romance-arc beats including explicit scenes. Time + narrative advance.

### Research / intel (run-specific Legwork)
- **Matrix research** — decker uses downtime on a host to dig up target data (skill checks; outcomes bank for the next run).
- **Streetwise canvas** — walk the neighborhood; dialogue with NPCs for intel.
- **Surveillance** — stake out a location for hours — gathers intel + time cost.

## Downtime UX

- **Time-blocking:** downtime consumes real-clock game time. Every action has an explicit time cost ("Train Firearms: 4 hours").
- **Schedule view:** UI shows upcoming appointments (rent due, contact appointments, scheduled run deadlines).
- **Batch downtime:** UI supports "pass time until X" — advance until rent due / contact available / run deadline.
- **Interrupts:** sometimes a downtime action is interrupted by a world event (contact call, job offer, violence near PC's apartment, landlord visit, addiction withdrawal).

## Downtime pacing

- After a run, expected downtime: several in-game days (2–7) before the next run surfaces (depends on fixer / job-board cadence).
- Player choice to sprint (accept next run ASAP, skip training) or pace (take time to train, build Loyalty, save up).

## MVP scope

- **Training:** skill raise action implemented; attribute raises stubbed.
- **Contact actions:** visit, call, favor available for all MVP contacts.
- **Shopping:** street doc, fence, dealer, fixer contacts have shops with MVP catalogues.
- **Sleep / rest:** implemented.
- **Sex-work session:** one venue (brothel / club) supports session-based earning. Paid work at minimal tier.
- **BTL / drug consumption:** implemented via item use; addiction ticks.
- **Romance visits:** one romance arc, 3–5 downtime beats + explicit scene.
- **Matrix / streetwise research:** available as Legwork before the MVP run.

## NSFW-aware downtime

Downtime is where the NSFW pillar lives day-to-day:
- Sex with romance contact (scheduled visits).
- Transactional sex-work sessions.
- BTL consumption / addiction loop.
- Drug use / addiction loop.
- Visit to the Barrens brothel / BTL studio as ambient content + potential intel.

These are all actions in the same menu as training and contact visits — not siloed.

## Open questions

- Training pace — how much downtime before a full Firearms raise?
- "Pass time" batch UX — confirm time-advance or skip through?
- Contact-maintenance time cost — light enough to not feel punishing?
- Addict recovery downtime — dedicated detox action vs. passive time + willpower tests?
- Romance-visit availability window — always available at threshold, or per-contact-schedule-gated?
- Can the PC "work" a day job for steady income (low-tier legit work for SINful PCs)?
- Long training stretches — can the PC lose a day / week to training without a run popping? What's the upper bound?
