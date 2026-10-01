# GB TEC Register Tracker

A longitudinal tracker of changes in NESO's Transmission Entry Capacity (TEC) Register, focused on Connections Reform gate progression, project movements, capacity, technology mix and geography.

## Why this project exists

A current TEC Register snapshot shows the queue at one point in time. This project preserves successive snapshots so that changes can be reconstructed: projects moving between Unassigned, Gate 1 and Gate 2; projects entering or leaving the register; connection-date changes; and shifts in the composition of the queue.

Tracking began on **9 August 2026**. The local archive reached **51 successful snapshots by 30 September 2026**. Two collection dates were missed because the NESO API endpoint could not be resolved: 19 August and 26 September.

## Initial baseline: 9 August 2026

The first snapshot contained **2,212 agreement rows** representing **2,069 unique projects**.

A key methodological issue was identified early: staged projects can appear on multiple rows while repeating cumulative project capacity. Simply summing every row inflated the apparent queue from **691.0 GW** on a project-deduplicated basis to **741.6 GW**. The analysis therefore separates project-level capacity from row/stage-level gate movements.

On the deduplicated baseline:

| Gate | Projects | Capacity | Share of capacity |
|---|---:|---:|---:|
| Unassigned | 1,283 | 403.3 GW | 58.4% |
| Gate 1 | 716 | 277.1 GW | 40.1% |
| Gate 2 | 70 | 10.6 GW | 1.5% |

Two early patterns stood out:

- **Battery storage:** 28.2% of total queue capacity, but 86.6% of Gate 2 capacity.
- **Scotland:** 25.1% of total queue capacity, but 74.6% of Gate 2 capacity.

These are snapshot observations, not causal conclusions.

## What the tracker monitors

The workflow is designed to identify:

- project-level movements between Unassigned, Gate 1 and Gate 2
- capacity moving into or out of a gate
- projects newly appearing in or disappearing from the register
- changes to project staging
- changes to earliest connection dates
- planning/status changes
- technology composition
- Transmission Owner / geographic patterns
- evolution of Gate 2 capacity over time

A deliberate distinction is made between **a project's overall gate classification** and **the MW attached to rows carrying a particular gate**, especially for staged projects.

## Example movements captured

The archive has captured movements including Fiddlers Ferry BESS, Neilston 400kV Greener Grid Park, Inch Cape Offshore Wind Farm, Royle Farm BESS and other projects changing gate status, as well as projects leaving the register and connection dates moving.

The purpose is not to infer a reason for every register change. The tracker records what changed in the published data; causal interpretation requires additional evidence.

## Repository structure

```
.
├── README.md
├── methodology/
│   ├── METHODOLOGY.md
│   └── AI_ASSISTANCE.md
├── scripts/
│   └── README.md
└── data/
    └── README.md
```

The working archive also contains the historical CSV snapshots, PowerShell/Python analysis scripts, generated reports and visual assets. These will be added selectively rather than dumping the entire working folder into the public repository.

## Methodology and reproducibility

See [methodology/METHODOLOGY.md](methodology/METHODOLOGY.md) for the treatment of staged projects, deduplication, gate classification and known limitations.

## AI assistance

The automation and analysis workflow was developed with substantial AI assistance. The project owner initiated the tracking project, selected the questions to investigate, maintained the archive, reviewed outputs and uses the results for ongoing GB energy-market analysis. The repository does **not** claim that all code was independently authored by the project owner.

See [methodology/AI_ASSISTANCE.md](methodology/AI_ASSISTANCE.md).

## Data source

Source data: **NESO Transmission Entry Capacity (TEC) Register**.

This is an independent analytical project and is not affiliated with or endorsed by NESO. Users should refer to NESO's current published data and documentation for authoritative information.

## Status

**Active.** Intended to be updated as new TEC Register snapshots and material changes become available.
