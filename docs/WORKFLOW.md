# Workflow Guide

## 1) Define experiment scope

For each experiment, write down:
- Study name (e.g. `energy_landscape`)
- Input datasets and coordinate system
- Group/population columns used by `geocontext(...)`
- `k` values
- Factor analysis and clustering settings

## 2) Configure environment

- Create `.env` from `.env.example`
- Ensure notebook dependencies are installed (pandas, numpy, matplotlib, sklearn, factor_analyzer, keyring if needed)

## 3) Data intake

In `tanum.ipynb`:
- Replace source-specific ingest cells with the new dataset paths/query logic
- Confirm coordinate column names are consistent
- Validate numeric columns before analysis

## 4) Feature generation (geocontext)

Use `geocontext(...)` to produce context features:
- Radius features per `k`
- Totals per `k`
- Group means/proportions and standard deviations

Output baseline file:
- `{experiment}_points_with_context.csv`

## 5) Dimension reduction and grouping

Run factor analysis and KMeans sections in notebook.
Export:
- `{experiment}_r{resolution}_factor_scores.csv`
- `{experiment}_r{resolution}_factor_loadings.csv`

## 6) Map output

Generate and save map HTML:
- `{experiment}_map.html`

## 7) Record reproducibility

Create one run log per execution from `docs/RUN_LOG_TEMPLATE.md`.
At minimum capture:
- Input data snapshot/date
- Parameter values
- Output filenames
- Observations/issues

## 8) Keep repo clean

- Commit notebook changes with concise messages
- Avoid committing large intermediate files unless needed
- Keep experiment outputs clearly prefixed by experiment name

## 9) Future hardening path

Planned refactor after Energy Landscape pilot:
- Move core analysis functions into `src/geocontext/`
- Add tests for validation and deterministic outputs
- Add a CLI runner for non-notebook execution
