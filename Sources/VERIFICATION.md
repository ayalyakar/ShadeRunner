# OCR / Transcription Verification TODO

Items flagged during Seattle Sourcebook ingestion (pages 6–21) that need user verification against the physical pages. Structured by severity. Each item maps to a `transcription_note:` field somewhere in `Data/Lore/` or a stub file.

Mark items as **✓ verified** + correct reading once resolved; I'll then update the data files.

---

## CRITICAL — canonical anchors affecting multiple records

- [ ] **p.6 · Renraku Maglev construction year.** Current: flagged as 2017 with "could be 2011" note. *Used in:* `Data/Lore/Metroplex/Seattle.yaml` travel_to_metroplex.modes[Train].construction_year.
- [ ] **p.14 · Thunder Tyer vs. Thunder Tyler.** Current: "Thunder Tyer" with cross-reference flag. *Used in:* Seattle.yaml history.awakening_war.guerrilla_war.leadership + awakening_war.salish_offensive_2015 + thunder_tyer_biography.
- [ ] **p.14 · "Kugri Sound Naval Shipyard" (Bremerton).** Current: flagged as likely misread of "Puget Sound Naval Shipyard". *Used in:* history.awakening_war.salish_offensive_2015.
- [ ] **p.18 · Marilyn Schults surname spelling.** Current: "Schults" with flag for possible "Schultz". *Used in:* `Data/Lore/NPCs/Marilyn Schults.yaml` (file name + all cross-refs).
- [ ] **p.19 · LTG "206/2206" format.** Current: interpreted as metroplex-prefix / Downtown-exchange pair. *Used in:* `Data/Lore/Districts/Downtown.yaml` facts.ltg_downtown_access.

---

## HIGH — named entities affecting standalone stubs

### Travel / transportation
- [ ] **p.9 · "Oarcoash Line" (boat passenger line).** Current: low confidence; could be "Orcas", "Oarcoach", similar.
- [ ] **p.9 · "Blueline Tours and Trips" (bus line).**
- [ ] **p.9 · "Whippet Bus Company" (bus line).**
- [ ] **p.9 · "Falcor Express" (bus line, partially NAN-owned).**
- [ ] **p.9 · "Detahx" (continental car-rental agency).**
- [ ] **p.9 · "Bolle Ferry" (ferry line, Seattle Public Ferry System).**
- [ ] **p.9 · "Renraku Loco Airlines" (intracity airline) — middle word.**

### Trid stations (p.13)
- [ ] **KONG** (NBS affiliate, Channel 4) — affiliation ("NBS" vs "NBC")
- [ ] **KOBD** (CBC affiliate, Channel 7) — callsign + affiliation
- [ ] **Channel 7 second station** — prose lists a second Channel-7 entry; resolve whether that's duplication or distinct station (KNBC/KING/etc.)
- [ ] **KSIS** (PBS, Channel 9)
- [ ] **KXSB** (independent, Channel 11)
- [ ] **KGTC** (independent, Channel 17)
- [ ] **KTAX** (independent, Channel 21)
- [ ] **KPLX** (public affairs, Channel 6)
- [ ] **NSBL** (Salish-Shidhe Lands network, Channel 13)

### Pleasure houses (p.13)
- [ ] **"Lord of Out-Style"** name + "Oak Pillar" district-hint
- [ ] **"Lucy's"** + "Texas Plaza" district-hint
- [ ] **"Bedlight"** name

### Chain names (pp.10–11) — entire catalog
The four-tier chain lists on pp.10–11 are mostly small-font body text. These all read at low confidence; resolve when convenient:

- [ ] p.10 · Department stores: Lordsmongs, Bloomleys, Fahran and Redress, The Bowes, Wordsworth, Laura and Mercies, Penley's, Meyers Superstores, Ray-Mart, Steve's Central
- [ ] p.10 · Groceries: Society Grocers, G. Meyers Gourmets, Advanson's Grocery, Curry & Save
- [ ] p.10 · Restaurants: Asenius International, Tokoni's, Inai's Seattle Dining, Toshona Fogliero's, La Gatetas, Fu Gour Club, Joseph Wong, Easy Ran, The Original Ester, Pol Tho's, Grade's for Ribs, Facanito McKusker's, Jiang Net Lee, The Bengalok Inlet, Jack and Rental's, Massilino's, Mankilder's, The Golden Axechins
- [ ] p.11 · Hotels Luxury tier — **entire line illegible** (needs the names transcribed)
- [ ] p.11 · Hotels: Hotel Trans, The Lost-Luxe, York Hotel, Motel 1998, Penn and Thor, Style's Castle Inn, Barne's Moneymunchers
- [ ] p.11 · Computers / Electronics: Suriette, R. Byler, Lyle's Computer Sorcerers, Sunrose Computer International, Hard-ware Sisters, Board Sisters Software, Microfiche Software, DeCore's Electronics, Haaren's Red Light, Hermedy's Cheap Electronics
- [ ] p.11 · Body Enhancement: St. George's Cyberwear Chains

### Ads / places
- [ ] **p.10 · Tuesdays restaurant LTG numbers:** 206 (10-33-3491) / 206 (50-59-2946)
- [ ] **p.13 · Run Run Shaw's restaurant** — cuisine + LTG (ad partly legible)
- [ ] **p.17 · The Other Place street address** — "181 Ave. & Union St." (likely "2nd Ave & Union St." mis-scan)
- [ ] **p.17 · The Other Place LTG** — "206 (34-5300)"
- [ ] **p.21 · Lucas' Palace intersection** — "Third Ave. & Virginia St." (likely Belltown real-world analog)
- [ ] **p.21 · Lucas' Palace LTG** — "206 (32-0411)"

---

## MEDIUM — history / events / named figures

- [ ] **p.10 · Bus-tunnel "1990s" built decade** (in-world — odd for a 2050 setting to cite 1990s; likely canon as-is but verify)
- [ ] **p.11 · Chamber of Commerce guide fee** — 1,000¥ value and the guide-program prose paragraph
- [ ] **p.11 · NACLU Seattle hotline** — "555-LVL115" digits (likely an alphanumeric mnemonic)
- [ ] **p.11 · Another BBS post attribution (Hotels tail)** — handle + timestamp partly illegible
- [ ] **p.12 · Liquor store weekend hours** — page only states Mon–Fri; weekends unstated
- [ ] **p.12 · Opera House sponsorship sentence** — prose implies Renraku sponsorship; partly illegible
- [ ] **p.12 · Venue names: Coriel's Pantheon, Vastrous Gaming, Orlonstoro**
- [ ] **p.12 · Seattle Madisons team** — sport + home venue details
- [ ] **p.12 · Screamers "Union Bowl" league** — league name + home venue
- [ ] **p.12 · Megastar names: "Lily Shuisha Suyu", "Comfortably Numb's"** — spellings
- [ ] **p.12 · Magazine: "The Booker Top"** — title
- [ ] **p.12 · Seattle Art Museum location** — "Volunteers Park" vs. "Volunteer Park"
- [ ] **p.13 · Seattle Post-Intelligencer vs News Intelligencer** — newspaper name (likely the canonical "Post-Intelligencer")
- [ ] **p.13 · Night-of-Rage year** — 2009 vs 2039 (canon = 2039)
- [ ] **p.13 · Ork-Dwarven 2041 schism event label** — exact event name / nature
- [ ] **p.14 · "Lost Eagle Militia" pretext** — 2010 US land-seizure justification entity name
- [ ] **p.14 · Salish-Shidhe War Council tribe list** — Salish / Makah / Norteño / Cree / Salish-Shakal? (last one low-confidence)
- [ ] **p.14 · "X5-32" seismic-magnitude shorthand** — at the Great Ghost Dance
- [ ] **p.15 · Thunder Tyer enlistment age + Colorado geography** — age-at-enlistment + stepmother-community location
- [ ] **p.15 · "Liquid refugee camps" phrase** — floating barges or a mis-scan?
- [ ] **p.16 · Bellevue / Renton / Kent "unanimous" qualifier** — early-2019 three-city vote
- [ ] **p.16 · Syndicate-interference paragraph** — Mafia / Yakuza attempts during 2019 Everett + Tacoma annexation votes
- [ ] **p.17 · SPD '23 dissolution year** — confirm
- [ ] **p.17 · Alameson signature quote** — exact wording of the anti-metahuman campaign statement
- [ ] **p.17 · "Alameson Branch" of Humanis** — branch name matching governor surname (canon-intentional?)
- [ ] **p.17 · "Hands of Fire" neo-magic group** — full description
- [ ] **p.18 · Humanis Information Service LTG** — "TGY 22-10-12-14"
- [ ] **p.18 · Alameson assassination** — is a culprit ever identified elsewhere in the book?
- [ ] **p.18 · Tacoma District warehouse fire** — was it spread from Seattle or independent?
- [ ] **p.18 · Week of Shame ~200 arrest count** — confirm digit
- [ ] **p.18 · "Week of Shame" label attribution** — refers to Hands of Fire's collapse or Lone Star's action?
- [ ] **p.18 · Schults public-vow phrasing** — object of the vow
- [ ] **p.19 · Smog "cleaner zones" phrase** — "fairy tale of the Snohomish District" likely OCR artifact
- [ ] **p.21 · Queen Anne Hill / Elliot Bay orientation** — spatial relationship

---

## LOW — BBS handles (easy to correct on reappearance)

Recording here for future reference — most are single-appearance and low-stakes:

- [ ] **p.9 · "Fast cash (11-15-13 / 5-15-50)"** — BBS attribution interpretation
- [ ] **p.11 · Hotels-tail BBS handle** — timestamp visible, handle illegible
- [ ] **p.13 · "Aza-ker Poseph"** — Ork-Underground tour-survivor post
- [ ] **p.15 · "Smiley"** — military-reluctance commentary
- [ ] **p.15 · "Canyon"** — asked the Thunder-Tyer question
- [ ] **p.15 · "Professor Stealth"** — historian-voice responder (**being promoted to NPC stub**)
- [ ] **p.15 · "Colonel Mendiola / Menlosla"** — NAN-guerrilla-magic reminiscence
- [ ] **p.15 · Exodus eyewitness (CHIS-98)** — handle partly illegible
- [ ] **p.16 · "Detective Law"** — annexation-vote documentary post
- [ ] **p.18 · "Alameson" post-assassination handle** — impersonator / family / staffer / fabricated?
- [ ] **p.18 · "Roger Nick"** — UCC-Schults-corruption critique
- [ ] **p.18 · "Doc-S Dot"** — sharper UCC-Schults critique
- [ ] **p.19 · "Woppke the Weatherman"** — weather-forecast voice (**recurring-persona candidate**)
- [ ] **p.19 · "Shogun"** — street-smart cynic rebuttal
- [ ] **p.21 · "Unamused Seattlite"** — Pyramids-and-Arcologies sarcasm

---

## Pipeline

Once you verify an item:
1. Tell me the correct reading.
2. I'll update the relevant `Data/Lore/` file(s) and remove the transcription_note.
3. If the verification changes a stub's name (e.g. "Schults" → "Schultz"), I'll rename the file via `git mv`.

Not all items need verification before continuing — low-severity ones can stay flagged forever. The CRITICAL + HIGH items are the ones most worth resolving before the next wave of stubbing.
