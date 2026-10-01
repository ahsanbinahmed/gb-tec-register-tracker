# Methodology

## 1. Source and snapshot approach

The working process downloads the NESO TEC Register and stores a date-stamped CSV snapshot. Keeping successive snapshots makes it possible to analyse changes that cannot be reconstructed reliably from a single current-state download.

The archive began in August 2026. Pre-September snapshots are retained privately.

## 2. Why deduplication is necessary

The TEC Register can contain multiple agreement/stage rows for one project. In the working dataset, the field `Cumulative Total Capacity (MW)` may repeat the project's cumulative capacity on multiple stage rows.

Therefore, summing that field across all rows can double count staged projects.

The private August archive demonstrated that raw row-level summation can materially overstate project-level queue capacity because staged projects can repeat cumulative capacity. Exact pre-September historical values are intentionally not published. The public analysis therefore collapses records to project level when reporting total project capacity.

## 3. Project identification

The working scripts use project identifiers to group rows belonging to the same project. One comparison implementation normalises the `Project Number` to its leading `PRO-<number>` component where available and otherwise falls back to the project identifier.

Because identifier treatment can materially affect deduplication, results should be checked when NESO changes register structure or identifiers.

## 4. Gate classification

For project-level summaries, a staged project is classified by its highest observed gate:

- Gate 2
- Gate 1
- Unassigned

This answers: **What is the furthest gate reached by any recorded stage of this project?**

It does not mean that every MW of a staged project has reached that gate.

## 5. Capacity moving through gates

For change analysis, project status and capacity movement are deliberately separated.

A project may have multiple stages carrying different gates. Reporting the entire project's cumulative capacity as having moved to Gate 2 can therefore overstate the actual gated capacity.

The comparison workflow consequently reports both:

1. **project-level gate transition**, and
2. **row/stage-level MW associated with Gate 2**.

This distinction was introduced after reviewing staged-project behaviour in the register.

## 6. Other changes tracked

Successive snapshots can be compared for:

- gate changes
- new projects
- projects no longer present
- number of stages
- earliest effective/connection date
- project status
- Transmission Owner
- technology and capacity composition

A disappearance from the register is reported as a disappearance. It should not automatically be interpreted as cancellation without corroborating evidence.

Likewise, a changed date or gate is a change in the published register, not by itself evidence of the underlying reason.

## 7. Missing snapshots

The downloader retries failed requests. The working archive records two missing dates through 30 September 2026:

- 19 August 2026
- 26 September 2026

Comparisons spanning a missing date therefore describe the difference between the nearest available snapshots, not necessarily the exact day on which a change occurred.

## 8. Analytical principle

The project distinguishes:

**Observed in the register** → directly supported by snapshot comparison.

**Calculated** → derived from published fields using the documented grouping/aggregation rules.

**Interpretation** → an analytical hypothesis requiring supporting evidence beyond the register.

This distinction should be retained in public posts and future analysis.
