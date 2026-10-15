# Astrovascular Response Dynamics — Computational Supplement

Code and simulated outputs accompanying **“Astrovascular Response Dynamics and Cognitive Reliability in Early Alzheimer's Disease.”** This repository provides a reproducible, reduced-model feasibility analysis of neural-drive-conditioned vascular-response dynamics. It does not contain patient data or a physiologically calibrated model of Alzheimer's disease.

## Run the analysis

The recorded execution environment used **Python 3.13.5**, NumPy 2.3.5, SciPy 1.17.0, Matplotlib 3.10.8, and pandas 2.2.3 (see `results/run_manifest.json`). Compatible package ranges are listed in `requirements.txt`; these are not a frozen environment lockfile.

From the repository directory, run:

```bash
python -m pip install -r requirements.txt
jupyter notebook Astrovascular_Final_Simulation.ipynb
```

In Jupyter, select **Restart Kernel and Run All Cells**. The notebook requires no external datasets. Run it from the repository directory: generated files are written relative to the **current working directory** into `figures/` and `results/`.

## Analysis and outputs

The notebook simulates a reference condition and four predefined perturbations across brief, sustained, and repeated-stimulation protocols. A neural-to-vascular finite-impulse-response predictor is calibrated on independent synthetic trials. The analysis reports two complementary summary measures:

- **M:** the difference between late and early means of the neural-drive-conditioned vascular residual.
- **S:** the logarithmic late-to-early vascular-response ratio relative to the corresponding predicted-response ratio, defined for positive window means.

Running all cells regenerates:

- `figures/Figure_S1_mechanism_trajectories.{png,svg}` — simulated trajectories across stimulation protocols.
- `figures/Figure_S2_M_vs_S.{png,svg}` — differences in M and S across mechanisms.
- `results/table_S2_mechanistic_contrasts.csv` — response and contrast summaries.
- `results/table_S3_duration_interactions.csv` — model-implied duration comparisons.
- `results/table_S4_shape_sensitivity.csv` — noise-calibrated S sensitivity diagnostics.
- `results/run_manifest.json` — configuration, random seeds, and software versions recorded during execution.

## Interpretation and reproducibility

All mechanism parameters and perturbations are illustrative. Observation noise is synthetic and temporally correlated; calibration and evaluation use separate simulated draws with specified random seeds. Monte Carlo flag rates quantify behavior under the chosen simulation conditions, **not** clinical diagnostic performance. The model does not establish astrocyte-specific causation, tissue oxygen delivery, or effects on cognitive reliability.

This publication-focused notebook reproduces the listed figures and tables. Additional exploratory parameter-fitting and identifiability analyses are retained in a separate development archive and are **not** reproduced by this repository. Refer to the accompanying manuscript and Supplementary Material for scientific interpretation.
