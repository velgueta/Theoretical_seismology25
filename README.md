# Theoretical Seismology 2025 — Wavefield Gradients

Reproducible code and notebooks for synthesizing 3-C seismograms, rotating to LQT, and estimating **strain** and **rotation** from far-field theory and **finite differences**. Includes geometry studies (spacing/aperture), bandwidth effects, and accuracy metrics (NRMSE).

## What’s inside
- **`notebooks/Homework1_Theoretical_seismology2025.ipynb`** – Main workflow (Parts D–F, figures).
- **Core functions (in the notebook)**:
  - `sdr_to_mt(...)`, `add_clvd_iso(...)` (moment tensors: DC, DC+CLVD+ISO)
  - `make_surface_array(...)`, `make_surface_array_from_lambdaS(...)` (station grids)
  - `enz_to_lqt_array(...)` (ENZ → L/Q/T)
  - Synthesis (far-field P+S via \(\dot M(t)\)), Theory: `strain_th_from_displacement(...)`, `omega_th_from_displacement(...)`
  - FD: `fd_strain(...)` (centered differences on surface arrays)
  - Plots: `plot_LQT_all_stations(...)`
  - Metrics: NRMSE vs. \(\Delta/\lambda_S\)

## How to run
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt        # numpy, scipy, matplotlib (extend if needed)
jupyter lab                            # open the notebook and run top→bottom

