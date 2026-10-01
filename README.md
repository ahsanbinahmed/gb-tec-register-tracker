# GB TEC Register Tracker

A longitudinal tracker of changes in NESO's Transmission Entry Capacity (TEC) Register, focused on Connections Reform gate progression, project movements, capacity, technology mix and geography.

## Why this project exists

A current TEC Register snapshot shows the queue at one point in time. This project preserves successive snapshots so that changes can be reconstructed: projects moving between Unassigned, Gate 1 and Gate 2; projects entering or leaving the register; connection-date changes; and shifts in the composition of the queue.

Tracking began on **9 August 2026**. The local archive reached **51 successful snapshots by 30 September 2026**. Two collection dates were missed because the NESO API endpoint could not be resolved: 19 August and 26 September.

## Historical archive policy

Tracking began in **August 2026**, before the public weekly series. The underlying August snapshots and derived historical analysis are intentionally retained privately rather than published in this repository. This preserves the value of the original archive while the public repository focuses on curated weekly updates from September 2026 onward.

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
├── weekly-updates/
│   └── README.md
└── data/
    └── README.md
```

The working archive also contains historical CSV snapshots, PowerShell/Python analysis scripts, generated reports and visual assets. **Pre-September raw snapshots and derived historical outputs are intentionally kept private.** Public updates are curated summaries rather than a mirror of the private archive.

## Methodology and reproducibility

See [methodology/METHODOLOGY.md](methodology/METHODOLOGY.md) for the treatment of staged projects, deduplication, gate classification and known limitations.

## AI assistance

The automation and analysis workflow was developed with substantial AI assistance. The project owner initiated the tracking project, selected the questions to investigate, maintained the archive, reviewed outputs and uses the results for ongoing GB energy-market analysis. The repository does **not** claim that all code was independently authored by the project owner.

See [methodology/AI_ASSISTANCE.md](methodology/AI_ASSISTANCE.md).

## Data source

Source data: **NESO Transmission Entry Capacity (TEC) Register**.

This is an independent analytical project and is not affiliated with or endorsed by NESO. Users should refer to NESO's current published data and documentation for authoritative information.

## Weekly updates

Public weekly summaries are available in [weekly-updates/](weekly-updates/). The first public series covers September 2026 onward; the August archive remains private.

## Status

**Active.** Intended to be updated weekly when new TEC Register snapshots and material changes are available.
