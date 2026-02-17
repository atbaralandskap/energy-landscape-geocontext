# AGENTS.md

This file gives coding agents a clear default workflow for this repository.
Adjust wording and strictness to your preferred style.

## 1) Project Overview And Structure

Purpose:
- Geographic context analysis around points/grids.
- Factor analysis, clustering, and map export.
- Next planned experiment: `energy_landscape`.

Main files and folders:
- `tanum.ipynb`: reference notebook workflow.
- `docs/WORKFLOW.md`: end-to-end process.
- `docs/ENERGY_LANDSCAPE.md`: experiment-specific plan.
- `docs/RUN_LOG_TEMPLATE.md`: reproducibility template.
- `docs/run_logs/`: run history.
- `karta_html/`: exported map outputs.
- `bilder/`: figures.

## 2) Build And Test Commands

Environment setup (example):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install pandas numpy matplotlib scikit-learn factor-analyzer keyring
```

Notebook workflow:
```powershell
jupyter lab
```

Git checks:
```powershell
git status
git add -A
git commit -m "<message>"
git push origin master
```

## 3) Helpful CLI Tools And MCP Servers

Preferred tools:
- `rg` for fast file/text search.
- `git` for source control.
- `python` for data checks and scripting.

When available, use MCP resources before external web search for repo context.

## 4) Workflow For Implementing A Feature

1. Read `README.md` and relevant `docs/*.md`.
2. Clarify scope, assumptions, and output filenames.
3. Make minimal, targeted changes.
4. Keep naming aligned with experiment ID, e.g. `energy_landscape_*`.
5. Validate results (schema checks, NaN/Inf checks, expected row counts).
6. Update docs and add a run log entry if behavior/workflow changed.
7. Commit with a clear message and push.

## 5) Pointers To Task-Specific Guidance

Use these first:
- `docs/WORKFLOW.md`
- `docs/ENERGY_LANDSCAPE.md`
- `docs/RUN_LOG_TEMPLATE.md`

If geocontext logic is changed:
- Document parameter changes and output column impacts.
- Note migration steps if old output names are affected.

## 6) Guardrails

- Do not delete user data files unless explicitly requested.
- Avoid broad refactors unless requested.
- Prefer reversible edits and clear diffs.
- Keep experiment artifacts reproducible and well named.
- Ask before destructive operations.

## 7) Commit Style

Use short, intent-first messages:
- `docs: refine energy landscape workflow`
- `feat: add context export for energy dataset`
- `fix: handle NaN in factor analysis matrix`

## 8) Definition Of Done

A task is done when:
- Requested change is implemented.
- Outputs are validated.
- Documentation is updated where needed.
- Repo is in a clean, understandable state for the next step.
