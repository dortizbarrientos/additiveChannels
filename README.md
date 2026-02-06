# Additive channels in curved fitness landscapes (v13): paper figures

This repository builds (or supplies) the **figure PDFs referenced by the v13 manuscript**:

> Ortiz-Barrientos & Cooper, “Additive Channels in Curved Fitness Landscapes” (GENETICS submission, v13)

It **does not** compile the manuscript PDF. Upload `mainv13.tex` to Overleaf (or compile locally) and point it at the figure PDFs produced here.

## What this repo does

Running the build creates:

`runCompiled/paper_figures/final/`

and ensures it contains the full set of **paper figure PDFs** used by `mainv13.tex`.

Some figures are **generated from code** (Matplotlib). A small number are currently provided as **canonical PDF assets** to preserve exact layout fidelity and/or because the upstream generator scripts are not included in this minimal package. The build copies those assets into the output folder when needed.

## Quick start (two commands)

### macOS / Linux
From the repository root:

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt && .venv/bin/python code/run_paper_figures.py
````

## Outputs

After running, you will have:

* `runCompiled/paper_figures/final/`
  Only the PDFs required by the paper (the clean set).

* `runCompiled/paper_figures/new/`
  A superset that may include additional “bonus” PDFs/PNGs produced by the scripts (e.g. annotated variants).

## Repository layout

* `code/paper_cold/`
  The figure-generation scripts (Matplotlib). These generate a subset of the paper figures directly.

* `code/run_paper_figures.py`
  The build driver. Runs the scripts, collects outputs, and copies any missing paper PDFs from `assets/`.

* `assets/`
  Canonical PDFs used when a figure is not regenerated in this minimal package (kept to preserve exact appearance).

* `empirical/`
  Small empirical inputs used by the worked example (included only if redistribution is acceptable).

* `runCompiled/`
  Build outputs (generated; should not be version-controlled).

## Figure provenance (high level)

* **Generated from code**: produced by the scripts in `code/paper_cold/` and collected by `code/run_paper_figures.py`.
* **Included as assets**: stored under `assets/` and copied into the output folder if not generated. This is intentional, to keep figure appearance identical to the manuscript.

## Using these figures with LaTeX / Overleaf

Option A (recommended): upload the contents of `runCompiled/paper_figures/final/` to Overleaf and keep the filenames unchanged.

Option B: if your `mainv13.tex` expects figures under `figures/new/`, either:

* create that folder in Overleaf and upload the PDFs there, or
* change the figure path in LaTeX to point to where you put them.

## Requirements

* Python 3.10+ recommended
* Packages: NumPy, Matplotlib (installed via `requirements.txt`)
