# Consciousness-Collapse-Reproducibility

Data repo for Consciousness Collapse: Loss of Consciousness as Impedance Catastrophe paper

[README.md](https://github.com/user-attachments/files/24947968/README.md)
# Consciousness Collapse — Repro Pack

https://doi.org/10.5281/zenodo.18422479

This repository packages the paper + a deterministic reproduction notebook for the core **collapse fit**.

## What’s included

- `paper/`
  -  Consciousness Collapse: Loss of Consciousness as Impedance Catastrophe.pdf
  - Consciousness_Collapse_Clarification_Addendum.pdf

- `data/`
  - `Data.pdf` — literature compilation / provenance (180-point source pool).
  - `constructed_eta_R_dataset.csv` - condensed analysis dataset (43 anchor points).

- `notebooks/`
  - `Consciousness_Collapse_Reproduction.ipynb` — clean, GitHub-ready notebook that:
    1) domain-normalizes η (z-score within each domain),
    2) fits the pooled logistic collapse,
    3) bootstraps a 95% CI for k.
 - RefactoredNetworkCollapse (1).ipynb
## Quick start (local)

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Then open the notebook:

```bash
jupyter lab
# open notebooks/Consciousness_Collapse_Reproduction.ipynb
```

## Data note (important)

For privacy / licensing reasons, this repo ships with a **CSV header placeholder**.
To reproduce the fit, place your real 43-row dataset at:

`data/constructed_eta_R_dataset.csv`

Required columns:
- `domain` (string)
- `eta` (float)
- `R` (float, 0–1)

Extra columns are allowed.

If you intend to publish the dataset, remove the `data/*.csv` line in `.gitignore`.

## Reproducibility clarification

The addendum explains why different η normalizations can yield numerically different k values:
if η' = aη + b, then k' = k / a.

The notebook reports k in the **domain-normalized η coordinate**.
