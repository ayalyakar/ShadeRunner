# DESIGN - Core Loop

## Decision

**DECIDED:** The core loop is a **hybrid** of three models that co-exist without a single dominant framing:

1. **Run-based** — classic SR job → legwork → run → payout cycle.
2. **Open city** — free-roam sprawl with emergent opportunities between structured runs.
3. **Lifestyle sim** — daily needs, payments, relationships, health; runs emerge from this fabric.

The player fluidly shifts between these without a mode switch. A "run" is just what happens when a job is accepted; a "day" is what happens otherwise.

## Canonical session shape (non-prescriptive)

A realistic session might look like:

1. Wake up at current lifestyle. Attend to needs (food, sleep debt, commlink, injury recovery).
2. Check messages — a fixer has a job, a contact owes a favor, rent is due tomorrow.
3. Decide: take the job, do legwork for a future job, meet a contact, train a skill, or explore.
4. If a run: meet the Johnson, negotiate, legwork, execute, payoff.
5. Downtime: pay bills, stash gear, heal, hit the street for gossip.
6. Simulation advances around the player at all times.

## Run phases (when one is active)

- **Meet** — Johnson framing, negotiation over nuyen, conditions, intel.
- **Legwork** — investigation, blueprints, bribes, tailing marks, social engineering.
- **Planning** — optional, with tools like case-board or crew briefing; affects run odds.
- **Execution** — the actual run: stealth / combat / hacking / social / mixed.
- **Extraction** — getting out alive with the take.
- **Payout** — getting paid, heat adjustment, fixer relationship shift, fallout.

Each phase can be skipped or botched; consequences feed back into world state.

## Loop interactions

- Finishing a run **changes the world** (reputation, faction shifts, heat, item movement, NPC fates).
- Failing a run generates **consequence cascade** (debt, injury, heat, rep loss; sometimes permadeath — see `Gameplay/DESIGN - Saves.md` and `Character/DESIGN - Aging.md`).
- Downtime activities **feed into future runs** (contacts unlocked, skills grown, gear built, rep cultivated).
- Every action ticks the clock and the sim.

## Open questions

- How explicit is the mode transition to the player — any UI signal, or fully invisible?
- How to prevent "optimal play = always run, never live" from collapsing the sim.
- How to make lifestyle-only play meaningful for players who want a breather decade.
- What keeps the loop fresh after 100+ runs — era transitions, new districts, aging mechanics?
