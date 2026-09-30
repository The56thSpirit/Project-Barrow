# Fusion Milestones — Verification Log

**Audit date:** 2026-09-30 · **Auditor:** Villhaze (subagent-assisted; coordinator reviewed every finding)
**Input:** `fusion-milestones.csv` (30 data rows) · **Output:** `fusion-milestones.verified.csv` (31 data rows; same 9-column schema)
**Method:** three subagents verified rows 1–10, 11–20, 21–30 in parallel against primary sources (peer-reviewed papers via DOI, official lab/government/company announcements, regulatory filings). Coordinator re-checked key primary URLs itself (ITER sector-module release confirmed opened; Helion Polaris release, CFS PJM announcement, PPPL PACMAN page, TAE $150M announcement confirmed via search results; General Catalyst, GlobeNewswire, BusinessWire pages quoted verbatim by subagents from opened pages).
**Taxonomy:** `peer_reviewed` / `preprint` / `press_release` / `trade_press` / `tracker_reported`.
Press releases, trade press, and tracker entries are reported claims, not verification.

## Verdict summary

- **Verified:** 24 rows (23 original + 1 newly added)
- **Corrected:** 3 rows (Row 8 date; Row 26 conditions dropped unverified sub-figure; Row 29 conditions rewritten)
- **Downgraded (reported claim, no primary found):** 2 rows (Row 10, Row 18)
- **Unverifiable:** 1 row (Row 14 — value emptied); Row 7 stale tracker claim kept with UNVERIFIABLE flag
- **Added:** 1 row (verified TAE $150M 2025-06-02 raise)

## Per-row results

### Row 1 — JET, fusion_yield, 69.26 MJ (2023-10-03) — VERIFIED
- Primary: EUROfusion announcement (row's existing source_url). Precise figure 69.26 MJ confirmed across EUROfusion/UKAEA-quoted reporting (pulse #104522, 2023-10-03 19:14 GMT; ~5 s burn, 0.2 mg fuel).
- Changed: notes now clarify the page text rounds to "69 MJ" while 69.26 MJ is the precise announced figure; no peer-reviewed paper found confirming the exact figure, so status stays `press_release`.

### Row 2 — JET, decommissioning (2023-12) — VERIFIED (source corrected)
- Event confirmed: final plasma experiments 18 December 2023; plasma operations concluded end of December 2023 (UKAEA-quoted reporting).
- Changed: `source_url` swapped to `https://www.world-nuclear-news.org/articles/jet-retires-after-40-years-and-105,842-pulses` (the old EUROfusion record URL did not cover the closure claim); `verification_status` press_release → `trade_press`; notes now flag that a direct UKAEA announcement URL was not located.
- Side note: secondary reports disagree on the final pulse number (105,842 vs 105,929) — date is consistent; not row-relevant.

### Row 3 — NIF, fusion_yield, 5.2 MJ (2024-02-12) — VERIFIED
- Primary: LLNL "Achieving Fusion Ignition" page (row's URL): "Feb. 12, 2024: An experiment produced an estimated 5.2 MJ—more than doubling the input energy of 2.2 MJ." Date, value, 2.2 MJ input, 4th ignition-era shot all match. No change.

### Row 4 — DIII-D, ai_control, 300 ms (2024-02-21) — VERIFIED (flagged discrepancy resolved; audit was wrong)
- Primary: Nature paper DOI 10.1038/s41586-024-07024-9 (row's URL). The paper explicitly states the tearing prediction model "could forecast the instability 300 ms before the disruption" (Fig. 4b, discharge 193277); 200 ms for discharge 193273. The "25 ms" figure is the DNN dynamic model's single-step prediction horizon — a third-party audit conflated two different quantities.
- Changed: notes rewritten to state this; honesty preserved via nuance: the 300 ms figure is from post-experiment analysis, and real-time avoidance in that discharge was limited by beam-power bounds.

### Row 5 — Xcimer Energy, funding_round, $100M (2024-06-04) — VERIFIED
- Primary: company's own BusinessWire release (row's URL): "$100 million in Series A financing led by Hedosophia." No change.

### Row 6 — ITER, schedule (2024-07) — VERIFIED (source upgraded)
- Primary: ITER Organization press conference 2024-07-03. Research operations 2034; full magnetic energy 2036; D-D 2035; D-T 2039; tungsten first wall — all match.
- Changed: `source_url` ipp.mpg.de → `https://www.iter.org/node/20687/new-baseline-prioritize-robust-start-exploitation`. Notes now flag that the "+EUR 5 billion" cost figure is from secondary reporting, not confirmed on iter.org.

### Row 7 — ITER, schedule, "first plasma late 2025" (2024-07) — UNVERIFIABLE as a current claim (kept with conflict flag)
- "First plasma late 2025" was a target only under the superseded 2016 ITER baseline; the July 2024 baseline replaced it with Start of Research Operation 2034. The tracker's combination (first plasma 2025 + D-T 2034 + 2039) matches no official baseline.
- Changed: notes rewritten — conflict flag kept, UNVERIFIABLE as a current schedule claim, stale-tracker explanation added. Row kept for transparency per the keep-conflicts rule.

### Row 8 — Pacific Fusion, funding_round, $900M (2024-11 → 2024-10-25) — CORRECTED (date)
- Value confirmed: >$900M Series A committed, General Catalyst-led, milestone-based tranches, pulsed magnetic inertial fusion, Fremont CA (Bloomberg 2024-10-25; GC's own investment page).
- Changed: `date` 2024-11 → **2024-10-25**; `source_url` neimagazine → `https://www.generalcatalyst.com/stories/our-investment-in-pacific-fusion`; `verification_status` trade_press → `press_release`; notes corrected (stealth exit was the Oct 25 announcement, not November).

### Row 9 — NIF, fusion_yield, 4.1 MJ (2024-11-18) — VERIFIED
- Primary: LLNL page (row's URL): "Nov. 18, 2024: A 2.2-MJ shot achieved fusion ignition at NIF for the sixth time, producing an energy yield of 4.1 MJ." No change.

### Row 10 — Helion, funding_round, $425M (2025-01) — DOWNGRADED (reported claim)
- No Helion-owned announcement of this round found. $425M (reported as Series F, January 2025, around Polaris turn-on; ~$1.03B total per PitchBook) corroborated by multiple reputable outlets (TechCrunch, GeekWire).
- Changed: notes rewritten to state value stands as a reported claim; investors list retained. Status stays `tracker_reported`.

### Row 11 — EAST, pulse_duration, 1066 s (2025-01-20) — VERIFIED
- Primary: Chinese Academy of Sciences official announcement (row's URL links the Jan 21, 2025 announcement): steady-state high-confinement plasma for 1,066 s; ~100 million °C; broke own 403 s 2023 record. No change.

### Row 12 — WEST (CEA), pulse_duration, 1337 s (2025-02-12) — VERIFIED
- Primary: CEA announcement (row's URL): 1,337 s on 12 Feb 2025; 50 million °C; +25% over EAST's 1,066 s; 2 MW heating. 22 min 17 s arithmetic checks. The 2.6 GJ injected figure is not in the CEA release but is consistent with 2 MW × 1,337 s ≈ 2.67 GJ and is reported by other reputable outlets. No change.

### Row 13 — NIF, fusion_yield, 5.0 MJ (2025-02-23) — VERIFIED
- Primary: LLNL page (row's URL): "Feb. 23, 2025: NIF achieved ignition for the seventh time… The 2.05 MJ shot yielded 5.0 MJ," target gain 2.44. No change.

### Row 14 — TAE Technologies, funding_round, $280M (2025) — UNVERIFIABLE (value emptied)
- No primary or reputable source found for a ~$280M TAE raise in 2025. The $280M figure matches TAE's **2021** milestone financing (per TAE company information) — exactly the conflation the original note warned about. The only verified 2025 TAE raise is $150M+ (June 2, 2025).
- Changed: `value` and `unit` **emptied**; notes rewritten with the UNVERIFIABLE verdict and cross-reference to the new verified row. Status stays `tracker_reported`. Nothing fabricated to fill the gap.

### Row 15 — NIF, fusion_yield, 8.6 MJ (2025-04-07) — VERIFIED
- Primary: LLNL page (row's URL): "April 7, 2025: The eighth ignition experiment… yield of 8.6 MJ with uncertainty +/− 0.45 MJ… 2.08 MJ… 456-terawatt peak power pulse… target gain of 4.13." Tungsten-gradient-doped diamond capsule confirmed by LLNL news article. No change.

### Row 16 — Wendelstein 7-X, triple_product, 43 s (2025-05-22) — VERIFIED (framing discrepancy confirmed on the primary page itself)
- Primary: EUROfusion announcement (row's URL): OP2.3 ended May 22, 2025; peak triple-product value sustained 43 s; ~90 frozen hydrogen pellets over 43 s (ORNL injector); 20–30 million °C.
- The walk-back is on the same page: a **30 June 2025 update** reports JET community members surfaced previously unpublished JET long pulses (up to 60 s sustained), concluding W7-X and JET are "joint leaders… on a par."
- Changed: notes now cite the dated update explicitly. Headline still says "world record" — noted, not smoothed.

### Row 17 — NIF, fusion_yield, 2.4 MJ (2025-06-22) — VERIFIED
- Primary: LLNL page (row's URL): LANL-led team; 2.4 MJ; ±0.09 MJ; burning plasma. The "9th ignition-era shot" numbering is not confirmed in sources — the original note already flags this; kept. No change.

### Row 18 — Helion (Orion), construction, 50 MW (2025-07) — DOWNGRADED (reported claim)
- No Helion-owned primary found. Groundbreaking (2025-07-30), Orion plant Malaga WA, planned 50 MW, Microsoft PPA targeting 2028 corroborated by GeekWire and Reuters; full-capacity timeline uncertain (Axios via GeekWire: possibly 2030).
- Changed: notes rewritten as DOWNGRADED reported claim. Value stands. Status stays `trade_press`.

### Row 19 — CFS, funding_round, $863M (2025-08) — VERIFIED
- Primary: CFS's own July 2026 $1B announcement (row's URL): "With this capital, and the $863 million the company raised last year, CFS has now raised a total of $4 billion." Timeline reconciles: 2021 Series B $1.8B → mid-2025 ~$2.1B (tracker figure, matching the original note) → Aug 2025 Series B2 $863M → Jul 2026 $1B → $4B total. Series B2 label and Aug 2025 date corroborated by Virginia Business / AccessIPOs (08/28/2025).
- Changed: notes rewritten with the CFS quote and the reconciled timeline. The original snapshot-date discrepancy is resolved.

### Row 20 — NIF, fusion_yield, 3.5 MJ (2025-10-01) — VERIFIED
- Primary: LLNL page (row's URL): "Oct. 1, 2025: LLNL achieved ignition at NIF for a 10th time… 3.5 MJ, ±0.17 MJ… 2.065 MJ laser energy… target gain of 1.74." No change.

### Row 21 — Helion (Polaris), plasma_temperature, 150 million degC (2026-02) — VERIFIED (source upgraded)
- Primary: Helion's company-issued BusinessWire release (2026-02-13): Polaris achieved 150 million °C and became the first privately developed fusion machine to demonstrate measurable D-T fusion. ~10× Sun's core checks out.
- Changed: `source_url` TechCrunch Disrupt promo → `https://www.businesswire.com/news/home/20260213457749/en/` (confirmed via independent search results quoting the release URL verbatim). Notes rewritten.

### Row 22 — NRC, regulatory (2026-02-26) — VERIFIED
- Primary: NRC-issued release (row's URL, already primary). Proposed rule "Regulatory Framework for Fusion Machines" published in Federal Register 91 FR 9476 on 2026-02-26; Docket NRC-2023-0071; comments through 2026-05-27; public meetings 2026-03-25 (virtual) and 2026-04-07 (in-person) per NRC news release 26-002.
- Changed: notes refined; "first dedicated framework" flagged as gloss (NRC describes it as augmenting the Part 30 byproduct-material framework).

### Row 23 — CFS, regulatory (2026-04) — VERIFIED (source upgraded)
- Primary: CFS announcement 2026-04-28: first fusion power plant developer to apply to connect to a major grid — application to PJM Interconnection for the first ARC plant (Fall Line Fusion Power Station, Chesterfield County VA).
- Changed: `source_url` off-topic techtimes funding article → `https://cfs.energy/news-and-media/commonwealth-fusion-systems-becomes-first-fusion-company-to-apply-to-pjm-interconnection-the-largest-u-s.-wholesale-electricity-market`; `verification_status` trade_press → `press_release`; notes rewritten.

### Row 24 — General Fusion (LM26), plasma_temperature, 0.72 keV (2026-06) — VERIFIED (source upgraded)
- Primary: company-authored technical paper (Howard et al., General Fusion Inc., 2026-06-22): Thomson scattering measured Te = 718 ± 80 eV at peak compression (shot LMC-11); AXUV-derived Te 634–688 eV. 0.72 keV ≈ 8.4 million °C conversion checks out. Next targets 1 keV → 10 keV → Lawson criterion confirmed.
- Changed: `source_url` stocktitan republish → company-hosted technical paper PDF; notes rewritten (paper is company-authored, **not** peer-reviewed — stated explicitly).

### Row 25 — Helion, funding_round, $465M (2026-06-04) — VERIFIED
- Primary: Helion's own newsroom page (row's URL): $465M Series G, Thrive Capital-led, $15.5B post-money, $1.5B total raised. No change.

### Row 26 — General Fusion, corporate (2026-07-13) — VERIFIED (source upgraded; unverified sub-figure dropped)
- Primary: General Fusion's company-issued GlobeNewswire release (2026-07-13): began trading on Nasdaq as GFUZ after the Spring Valley Acquisition Corp. III merger; ~$150M cash ("inclusive of net transaction proceeds from the private placement and trust capital"); funds LM26 milestones through 2028.
- Changed: `source_url` prismmarketview → GlobeNewswire company release; `verification_status` trade_press → `press_release`; conditions rewritten to **drop the "$108M PIPE" sub-figure**, which could not be confirmed in the primary release (only the ~$150M total is sourced).

### Row 27 — ITER, construction, 6 sector modules (2026-07-28) — VERIFIED (source upgraded)
- Primary: ITER Organization release 2026-07-29 (confirmed opened by coordinator): "successfully installed the sixth of nine tokamak sector modules… lifting operation… concluded on 28 July"; almost six months ahead of schedule; final module now expected mid-2027.
- Changed: `source_url` engineeringnews.co.za → `https://www.iter.org/two-thirds-iter-tokamak-core-now-place`; `verification_status` trade_press → `press_release`; date kept as 2026-07-28 (installation conclusion).

### Row 28 — CFS, funding_round, $1000M (2026-07-30) — VERIFIED
- Primary: CFS's own announcement (row's URL): $1B additional equity financing; with the $863M "raised last year," total = $4B; ~30% of total private fusion investment; largest fusion round since CFS's own $1.8B Series B (2021). No change.

### Row 29 — DIII-D, ai_control, 20 ms (2026-09-02) — CORRECTED (conditions overstated)
- Primary: PPPL announcement (2026-09-02): "the whole PACMAN framework typically runs in about 20 milliseconds"; TM predicted ~200 ms before formation; 5 experiments; RL model took full heating control; density/rotation targets held. Underlying paper: Nuclear Fusion DOI 10.1088/1741-4326/ae7f9d (July 2026); preprint arXiv:2511.08818 (Nov 2025).
- Correction: the paper reports **different cycle times per controller** — RL 50 ms (20 Hz), MPC profile 20 ms (50 Hz), ELM predictor 2 ms, AE ~5 ms, TM inference <10 ms. Only the profile-control experiment ran at 20 ms / 50 Hz, so "full heating control loop at ~50 Hz **across 5 experiments**" was an overstatement.
- Changed: `source_url` tbsnews.net → PPPL announcement URL (confirmed via search); `verification_status` trade_press → `press_release`; `conditions` rewritten with per-controller cycle times; notes rewritten with DOI/arXiv and the "shot dates not published" confirmation (paper names shot 204975, no date).

### Row 30 — Helion, funding_round, $500M (2026-09-15) — VERIFIED (source upgraded)
- Primary: Helion's own newsroom page (same URL as Row 25, now carrying the update): "Helion closed its oversubscribed Series G at $500M in September 2026, up from an initial close of $465M." Corroborated by GeekWire 2026-09-15 (+$35M; CEO LinkedIn: crossover, pension, sovereign wealth investors). $465M + $35M = $500M is consistent with Row 25.
- Changed: `source_url` geekwire → Helion newsroom page; `verification_status` trade_press → `press_release`; notes rewritten.

### Row 31 (NEW) — TAE Technologies, funding_round, $150M (2025-06-02) — VERIFIED (added)
- Primary: TAE's own announcement (tae.com, 2025-06-02, confirmed via search): "raised more than $150 million in its latest funding round, exceeding the company's initial target"; Chevron Technology Ventures, Google, NEA participated; option to raise more; >$1.3B equity raised since inception.
- Added during this audit to replace the unverifiable $280M 2025 claim (Row 14). Distinct from the 2021 $280M milestone financing — do not conflate.

## Outstanding gaps / follow-ups

1. **Row 2:** a direct UKAEA announcement URL for JET's final plasma day was not located; the WNN article quotes UKAEA. If a UKAEA page surfaces, upgrade.
2. **Row 6:** the "+EUR 5 billion" ITER cost-increase figure rests on secondary reporting only.
3. **Row 16:** the EUROfusion headline still says "world record" while its own update says "on a par" with JET — worth re-checking if IPP publishes the peer-reviewed papers.
4. **Row 24:** the General Fusion technical paper is company-authored, not peer-reviewed; watch for a journal publication.
5. **Rows 14/31:** watch for TAE's Trump Media merger close (announced Dec 2025, expected before end of 2026) — a future corporate row, not this audit's scope.
6. **Source freshness:** press-release values remain reported claims per the provenance rules, even where the source is primary (company/lab announcements are self-reported).

## Files

- `fusion-milestones.verified.csv` — 31 data rows, 9 columns, no missing `source_url`, validated programmatically.
- Original `fusion-milestones.csv` left untouched.
