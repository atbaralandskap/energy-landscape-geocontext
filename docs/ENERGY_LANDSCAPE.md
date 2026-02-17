# Energy Landscape Experiment Plan

This document defines how to reuse GeoContext for the upcoming **Energy Landscape** experiment.

## Experiment ID

- `energy_landscape`

## Intended outputs

- `energy_landscape_points_with_context.csv`
- `energy_landscape_r8_factor_scores.csv`
- `energy_landscape_r8_factor_loadings.csv`
- `energy_landscape_map.html`

## Execution checklist

1. Prepare input data with valid coordinate columns (`east/north` or mapped alternatives).
2. Confirm group columns and population columns for `geocontext(...)`.
3. Set `kValues` for neighborhood context.
4. Run geocontext section.
5. Run factor analysis section.
6. Run clustering section.
7. Export map and CSV outputs.
8. Log run details.

## Data contract (minimum)

Input points table:
- Unique ID column (`hex_id` or equivalent)
- Coordinate columns

Population/location table:
- Coordinate columns
- Population weight column(s)
- Group columns for context metrics

## Quality checks before publishing results

- No missing coordinates in used rows
- No non-numeric values in analysis columns
- No unexpected NaN/Inf in factor analysis matrix
- Cluster labels present for all expected rows

## Open decisions to finalize before first run

- Final variable dictionary for energy-related group columns
- Geographic resolution(s) to compare (e.g. r8 only or multiple)
- Number of factors and KMeans clusters
- Inclusion/exclusion criteria for sparse cells
