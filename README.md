# ODER: Observer-Dependent Entropy Retrieval for Linguistic Computation

**Version 1.1.0**

This release enables direct, falsifiable testing of ODER predictions on controlled linguistic-entropy data. ODER implements an observer-dependent entropy-retrieval model for language comprehension, explicitly parameterizing attention, working memory, and prior knowledge in trace-based benchmarks.

**This repository accompanies**

```
Cooper, Evlondo. (2025). Observer-Dependent Entropy Retrieval in Linguistic Computation:  
A Foundational Framework and Benchmarking Methodology.  
https://doi.org/10.5281/zenodo.15428312
```

---

### Quick Start

**Main Framework Reproduction**

Use this notebook to replicate all quantitative results, figures, and diagnostics from the main study.

*Notebook*: `ODER_Linguistic_Framework.ipynb`

* Run all cells to generate entropy traces, observer-dependent fits, and comparative baselines.
* Output plots and tables are saved to the `figures/` directory.
* Reproduces model-fit tables and figures reported in the manuscript.

**Interactive Playground**

Exploratory fitting, falsification, and parameter-sensitivity analysis.

*Notebook*: `ODER_Interactive_Playground.ipynb`

* Fit ODER curves to arbitrary sentence traces and observer classes.
* Detect collapse points, visualize N400/P600 mapping, and run bootstrap validation.
* All outputs are sandboxed; publication data is not altered.
* Requires `ipywidgets` for interactive controls.

**Natural Stories Validation**

Tests ecological validity by applying fixed Aurian parameters to Natural Stories sentences with reading-time data.

*Notebook*: `ODER_Natural_Stories_Validation.ipynb`

* Loads a small Natural Stories subset plus targeted stress-test sentences.
* Computes collapse-time error (Δτ\_res), RMSE, and shape-mismatch flags.
* **Expected results:**

  * Median |Δτ\_res| ≈ 0.6 s
  * Median RMSE ≈ 0.46
  * Most stress-test items flagged for shape mismatch
  * Largest divergence: `ns_001` with +4.0 s offset

---

### Installation

```bash
pip install -r requirements.txt
```

Tested on Python 3.10+. Create a fresh environment to avoid dependency conflicts.

---

### Data

* **Natural Stories subset**: sentences with per-token reading times (ms).
* **Stress-test items**: hand-constructed sentences (garden-path, center embedding, coordination ambiguity).

*No eye-tracking data are included in this repository.*

---

### Theoretical Framework

ODER models comprehension as **observer-dependent entropy retrieval**, not prediction error or static syntactic complexity. The governing law is

```
dS_ret/dτ = γ(τ) [S_max − S_ret(τ)] tanh(τ / τ_char)
```

**Parameters**

* τ\_char — Characteristic retrieval timescale (processing effort)
* γ(τ)   — Observer-dependent retrieval rate
* S\_max  — Maximum retrievable entropy per sentence/trace

**Inverse decoder**

From an observed entropy trajectory, the retrieval-rate profile can be recovered as:

```
γ(τ) = (dS_obs/dτ) / [(S_max − S_obs(τ)) tanh(τ / τ_char)]
```

**Collapse point**

Collapse is marked at S\_ret(τ\_res) ≥ 0.95 S\_max with 400 ms steps, aligning τ\_res with standard N400/P600 ERP windows.

---

### Simulation Features

* **Aurian corpus**: synthetic, controlled language with adjustable complexity
* **Observer classes**: high vs. low context with distinct γ, τ\_char, and noise levels
* **Baseline comparisons**: linear, exponential, power-law fits
* **Diagnostics**: stress flags, failure taxonomy, parameter sensitivity sweeps

**Visualizations**

* Entropy retrieval curves by observer and sentence type
* Collapse-point detection and ERP window mapping
* Failure taxonomy tables with root-cause notes
* RMSE histograms and Δτ\_res error distributions

---

### Repository Structure

| File                                    | Description                                       |
| --------------------------------------- | ------------------------------------------------- |
| `ODER_Linguistic_Framework.ipynb`       | Main framework reproduction (all results)         |
| `ODER_Interactive_Playground.ipynb`     | Interactive fitting and falsification environment |
| `ODER_Natural_Stories_Validation.ipynb` | Validation on Natural Stories reading-time data   |
| `requirements.txt`                      | Python dependencies                               |
| `figures/`                              | Output directory for plots and visualizations     |

---

### Extending the Framework

* **Modify corpus** — add new sentences, languages, or observer classes
* **Parameter exploration** — probe sensitivity, neurodivergent bands
* **Model development** — generalize retrieval laws, adapt failure taxonomy
* **Empirical mapping** — apply to EEG, reading-time, or behavioral corpora

---

### Citation

```
Cooper, Evlondo. (2025). Observer-Dependent Entropy Retrieval in Linguistic Computation:  
A Foundational Framework and Benchmarking Methodology.  
https://doi.org/10.5281/zenodo.15428312

Cooper, Evlondo. (2025). ODER Linguistic Framework v1.1.0 — Benchmarking Suite with Natural Stories Validation.  
Zenodo. https://doi.org/10.5281/zenodo.[new_DOI]
```

---

### License

MIT License — see `LICENSE` for details.

---

### Contact

Evlondo Cooper
[evlocoo@pm.me](mailto:evlocoo@pm.me)

---
