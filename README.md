# Energy Landscape GeoContext

GeoContext is a research workspace for geographic context analysis around points/grids, with outputs for factor analysis, clustering, and map visualization.

Current repository status:
- Main analysis notebook: `tanum.ipynb`
- Exported map: `karta_html/tanum_byggnadsar.html`
- Example outputs and datasets: `tanum_*`, `bornholm_*`
- Figures: `bilder/`

## Goal of this cleanup

This repository is now documented as a reusable analysis base.
The next planned study is **Energy Landscape**, which will run the same geocontext workflow on new input data.

## Suggested working model

1. Treat `tanum.ipynb` as the reference workflow.
2. Keep raw/experimental datasets out of Git unless they are small and intentionally versioned.
3. Save derived outputs with clear experiment names.
4. Track each experiment in a dedicated run log.

## Repository layout (current + recommended)

Current files are preserved. Recommended additions for ongoing work:

- `docs/WORKFLOW.md`: end-to-end process for running and extending analysis
- `docs/ENERGY_LANDSCAPE.md`: concrete setup for the Energy Landscape experiment
- `docs/RUN_LOG_TEMPLATE.md`: template for reproducible run notes

## Quick start for a new experiment

1. Copy `.env.example` to `.env` and fill database credentials.
2. Open `tanum.ipynb` and duplicate/adapt the data-ingest cells for new data.
3. Run geocontext features, factor analysis, and clustering.
4. Export outputs with an experiment prefix, e.g. `energy_landscape_r8_factor_scores.csv`.
5. Add a run note using `docs/RUN_LOG_TEMPLATE.md`.

## Naming convention for new outputs

Use this pattern to keep artifacts grouped:

- `{experiment}_points_with_context.csv`
- `{experiment}_r{resolution}_factor_scores.csv`
- `{experiment}_r{resolution}_factor_loadings.csv`
- `{experiment}_map.html`

Example for this project stage:
- `energy_landscape_points_with_context.csv`
- `energy_landscape_r8_factor_scores.csv`
- `energy_landscape_r8_factor_loadings.csv`
- `energy_landscape_map.html`

## Next technical step (recommended)

When you are ready, extract `geocontext(...)` from the notebook into a Python module (`src/geocontext/core.py`) so Energy Landscape runs are scriptable and testable.

