# Open Datasets for the Barrow-scale Effort

**Maintainer:** Villhaze · **Started:** 2026-09-30
**Purpose:** structured, source-pinned datasets aggregating published results in fields that advance humanity's Barrow-scale standing — built as open resources for the researchers in those fields.

## Provenance rules (non-negotiable)
1. **Every row carries its source.** A row without a `source_url` does not ship.
2. **Verification status is explicit:** `peer_reviewed` / `preprint` / `press_release` / `trade_press` / `tracker_reported`. Press-release and trade-press values are *reported claims*, never stated as fact.
3. **No fabrication, ever.** If a value isn't in the source, the cell stays empty — never inferred, never interpolated silently. Estimates are labeled `~` with the basis in `notes`.
4. **Date-stamped.** Every row has an event/publication date; the file header records `last_updated`.
5. **Conflicts are kept, not smoothed.** When sources disagree, keep both rows and note the discrepancy.
6. **Update log** at the bottom of this file records every population/update pass.

## Datasets

### 1. `fusion-milestones.csv` — Fusion progress evidence table
Dated records of fusion yields, triple products, pulse durations, plasma-control results, and funding rounds — the V-minus foothold ledger.
Columns: `date, facility_or_company, milestone_type, value, unit, conditions, source_url, verification_status, notes`

### 2. `2d-transistor-benchmarks.csv` — 2D materials device benchmarks (2024–2026)
Device metrics mined from the 2D-transistor literature — the IV-minus device frontier table the field lacks.
Columns: `date, paper_doi_or_url, material, mobility_cm2_Vs, on_off_ratio, contact_resistance_ohm_um, channel_length_nm, growth_method, transfer_method, source_url, notes`

### Planned
- `particle-anomalies.csv` — live anomaly registry with version-pinned theory baselines (Belle II B⁺→K⁺νν̄, R(D(*)), C₉ fits, W-mass, g−2).
- `quantum-sensing-records.csv` — sensitivity records by modality/measurand.
- `mechanosynthesis-runs.csv` — SPM/mechanosynthesis attempt parameters and outcomes.

## Update log
- 2026-09-30: directory + schemas established; datasets 1–2 population delegated.
- 2026-09-30: `fusion-milestones.csv` populated with 30 rows (2023–2026; yields, pulse durations, triple product, plasma temperatures, AI control, funding, regulatory, construction, corporate, decommissioning, schedule). Known conflict rows kept: ITER 2024 baseline vs tracker first-plasma claim. Verification mix: 18 press_release, 1 peer_reviewed, 8 trade_press, 3 tracker_reported.
- 2026-09-30: `2d-transistor-benchmarks.csv` populated with 33 rows (27 in-window 2024–2026 + 4 labeled pre-2024 baselines + 1 program row + moiré ecosystem rows). Empty cells where numbers weren't reported; kΩ·µm converted to ohm·µm; secondary/approximate entries flagged in notes. Gaps for follow-up: Kong 2026 dry-transfer DOI, 35 nm nanoribbon + solution-processed FET DOIs, more 2024–2025 entries (TSMC IEDM, imec, WS₂ contacts, MoS₂ RF).
