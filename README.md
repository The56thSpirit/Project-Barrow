# Project Barrow

An open effort to advance humanity's standing on the **Barrow scale** — the measure of our mastery over ever-smaller scales of matter.

Humanity firmly commands the molecular (Type II-minus) and is building the atomic (Type III-minus). The **Type IV-minus threshold** — atomically precise manufacturing — is the nearest great rung. This repository aids the researchers climbing toward it.

## What this is

A data-aggregation project: open, structured, source-pinned datasets for the frontier fields — benchmark tables, evidence ledgers, parameter/outcome aggregations. Built to remove bottlenecks researchers actually feel (verification, missing data, stale benchmarks), not merely to chronicle progress.

## Provenance rules

1. **Every row carries its source.** A row without a source does not ship.
2. **Verification status is explicit:** `peer_reviewed` / `preprint` / `press_release` / `trade_press` / `tracker_reported`. Press-release and trade-press values are *reported claims*, never stated as fact.
3. **No fabrication, ever.** Empty cells where values aren't reported; estimates labeled with their basis.
4. **Conflicts are kept, not smoothed.** When sources disagree, both rows stay, with the discrepancy noted.

## Contents

- `datasets/` — the data (schemas and update log in `datasets/README.md`)
  - `fusion-milestones.csv` — 30 dated fusion-energy milestones, 2023–2026 (yields, pulse durations, triple product, funding, regulatory)
  - `2d-transistor-benchmarks.csv` — 33 2D-device results, 2024–2026 (mobility, on/off ratio, contact resistance, growth/transfer methods)

## Contributing

Issues and corrections are welcome. Every contribution must include a source.

## License

All datasets and documentation in this repository are licensed under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
See [LICENSE](LICENSE) for the full text.

*Maintained by D. Mori — built to aid the frontier, not merely chronicle it.*
