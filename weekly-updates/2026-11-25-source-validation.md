# TEC Register source validation — 25 November 2026

The official CSV named `tec-register-23-november-2026.csv` was acquired on 25 November. The downloader log records successful retrieval of the official resource and DataStore, each with 2,186 rows, and distinct SHA-256 hashes. The official file is now the primary source; DataStore is a secondary check. Different hashes require semantic comparison, not automatic rejection.

## Validated official aggregate

- 2,050 normalised projects: 965 ungated, 930 Gate 1, 155 Gate 2.
- Project-total capacity: 676,318.44 MW (maximum cumulative capacity per base project number).
- Row-sum capacity: 676,318.47 MW (MW Connected plus MW Increase / Decrease).
- Difference: 0.03 MW.
- Relative to the 22 November acquired snapshot: one fewer project, 76.50 MW lower capacity; two ungated projects moved to Gate 2 (96.9 MW project-total), one to Gate 1 (710 MW), and one 49.5 MW listing disappeared. Register changes do not establish offers or cancellations.

## Archive coverage and limitations

107 daily acquisitions from 9 August to 25 November, 33 distinct byte hashes, missing acquisition dates 19 August and 26 September. Daily acquisition coverage is 107/109 (98.17%). This is not publication coverage. Repeated hashes can reflect unchanged releases. Earlier official publication history is not independently verified. The 23–24 November acquisitions retained an older version than the official file obtained on 25 November; exact source synchronisation timing is unknown. Preserve all original snapshots and distinguish publication from acquisition dates.

## Weekly QA

Retrieve official resource dynamically; retain source metadata and hashes; compare secondary source semantically; check schema, missing dates, duplicates, gate classification, additions/removals and both capacity calculations. Investigate material discrepancies before publishing. Publish aggregates only. Gate classifications use highest observed label per base project; whole-project capacity is not gate-labelled row capacity.
