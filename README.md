**ODER: Observer-Dependent Entropy Retrieval for Linguistic Computation**

**Version 1.2.0**

This release adds a dedicated benchmarking suite for falsifiable comparison against both analytic and mechanistic foils. 

ODER implements an observer-dependent entropy-retrieval model for language comprehension, explicitly parameterizing attention, working memory, and prior knowledge in trace-based benchmarks.

This repository accompanies:
Cooper, Evlondo. (2025). *Observer-Dependent Entropy Retrieval in Linguistic Computation: A Foundational Framework and Benchmarking Methodology*.
[https://doi.org/10.5281/zenodo.15428312](https://doi.org/10.5281/zenodo.15428312)

---

**Quick Start**

**Main Framework Reproduction**
Notebook: `ODER_Linguistic_Framework.ipynb`

• Replicates all quantitative results, tables, and figures from the main study

• Generates entropy traces, observer-dependent fits, and ΔAIC comparisons

• Outputs are saved to the `figures/` directory

**Interactive Playground**
Notebook: `ODER_Interactive_Playground.ipynb`

• Real-time fitting for arbitrary traces and observer classes

• Collapse-point detection, N400/P600 mapping, and bootstrap validation

• Requires `ipywidgets` for interactive controls

**Natural Stories Validation**
Notebook: `ODER_Natural_Stories_Validation.ipynb`

• Applies fixed Aurian parameters to real English sentences with reading-time data

• Reports collapse-time error (Δτ\_res), RMSE, and shape-mismatch flags

• Includes stress-test cases (garden-path, center embedding, ambiguity)

**Baseline Foils Benchmarking**
Notebook: `ODER_Linguistics_Baseline_Foils.ipynb`

• Benchmarks ODER against linear, exponential, power-law, surprisal-aligned exponential, and ACT-R decay baselines

• Reproduces Table X and Figure `figmodel_fits` from the manuscript

• All fits use identical bounds, optimizers, and trace inputs

---

**Installation**

```
pip install -r requirements.txt
```

Tested on Python 3.10+. Use a clean environment to avoid conflicts.

---

**Data**

• Natural Stories subset (with per-token reading times)

• Hand-constructed stress-test items (e.g., garden-path, coordination ambiguity)

No eye-tracking or EEG data is included in this repository.

---

**Theoretical Framework**

ODER models comprehension as observer-dependent entropy retrieval. The governing law:

  dS\_ret/dτ = γ(τ) · \[S\_max − S\_ret(τ)] · tanh(τ / τ\_char)

**Key parameters:**

• γ(τ): retrieval rate

• τ\_char: characteristic processing time

• τ\_res: collapse point (≥ 95% retrieval)

• S\_max: max retrievable entropy per trace

**Inverse decoder:**

  γ(τ) = (dS\_obs/dτ) / \[(S\_max − S\_obs(τ)) · tanh(τ / τ\_char)]

---

**Simulation Features**

• Aurian: controlled synthetic language with adjustable complexity

• Observer classes: O1/O3 with distinct γ, τ\_char, and noise profiles

• Baselines: linear, exponential, power-law, ACT-R, surprisal

• Diagnostics: convergence rate, stress flags, failure taxonomy

---

**Visualizations**

• Retrieval curves by observer and sentence type

• Collapse-point alignment with ERP windows

• ΔAIC fit comparisons across models

• RMSE and Δτ\_res histograms

• Trace-by-trace failure taxonomy

---

**Repository Structure**

• `ODER_Linguistic_Framework.ipynb` — Reproduces all core results and figures

• `ODER_Interactive_Playground.ipynb` — Interactive fitting and collapse diagnostics

• `ODER_Natural_Stories_Validation.ipynb` — Ecological validation with reading-time data

• `ODER_Linguistics_Baseline_Foils.ipynb` — Matched benchmarking of analytic/mechanistic foils

• `requirements.txt` — Python dependencies

• `figures/` — Output directory for plots and visualizations

---

**Extending the Framework**

• Add new stimuli, languages, or observer classes

• Generalize the retrieval law (e.g., piecewise γ(τ))

• Apply to EEG, reading-time, or behavioral corpora

• Build cross-domain benchmarks from ERP or eye-tracking datasets

---

**Citation**

Cooper, Evlondo. (2025). *Observer-Dependent Entropy Retrieval in Linguistic Computation: A Foundational Framework and Benchmarking Methodology*.
[https://doi.org/10.5281/zenodo.15428312](https://doi.org/10.5281/zenodo.15428312)

Cooper, Evlondo. (2025). *ODER Linguistic Framework v1.2.0 — Full Benchmarking Suite*.
Zenodo. [https://doi.org/10.5281/zenodo.\[new\_DOI](https://doi.org/10.5281/zenodo.[new_DOI)]

---

**License**
MIT License — see LICENSE for details.

---

**Contact**
Evlondo Cooper
[evlocoo@pm.me](mailto:evlocoo@pm.me)
