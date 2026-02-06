# additiveChannels
Aimed for a Special Issue for GENETICS on Fitness Landscapes

# Additive channels in curved fitness landscapes (v13)

Code + figure assets for the manuscript:

> Ortiz-Barrientos & Cooper, “Additive Channels in Curved Fitness Landscapes” (GENETICS submission, v13)

This repository aims to support replication of the **computational results and diagnostics** used in the paper, and to provide the **final figure PDFs** used to compile the manuscript.

## What you can reproduce here

1) **Core computations**
- Gaussian selection operator on phenotypes (within-generation update)
- Quadratic selection operator on breeding values (optional / level-1)
- Additivity index 𝒜g and its variance decomposition

2) **Code-generated demonstration figures**
A small set of reproducible “from-code” figures illustrating the main mechanics.

3) **Manuscript build**
The LaTeX source (`mainv13.tex`) plus the figure PDFs it includes (see `figures/new/`).

> Note: several manuscript figures are assembled as vector graphics (schematics / multi-panel layouts). Those PDFs are included as assets, but the exact PDF layout may not be regenerated purely from the Python scripts unless the corresponding design sources (e.g. SVG) are added.

---

## Quick start (two commands)

### macOS / Linux
```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt && .venv/bin/python run_all.py
