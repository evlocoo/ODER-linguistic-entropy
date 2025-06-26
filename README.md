**ODER: Observer-Dependent Entropy Retrieval for Linguistic Computation**

Version 1.0 

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

Use this notebook to replicate all quantitative results, figures, and diagnostics from the paper.

*Notebook*: `ODER_Linguistic_Framework.ipynb`

* Run all cells to generate entropy traces, observer-dependent fits, and comparative baselines.
* Output plots and tables are saved to the `figures/` directory (created automatically if absent).
* Reproduces Figures 1–4 and all model-fit tables in the manuscript.

**Interactive Playground**

Use this notebook for exploratory fitting, falsification, and parameter-sensitivity analysis.

*Notebook*: `ODER_Interactive_Playground.ipynb`

* Fit ODER curves to arbitrary sentence traces and observer classes.
* Detect collapse points, visualize N400/P600 window mapping, and run bootstrap validation.
* All outputs are sandboxed; publication data is not altered.
* Interactive controls (sliders, dropdowns) work in Jupyter Lab or classic Jupyter Notebook with *ipywidgets* enabled.

---

### Installation

```bash
pip install -r requirements.txt
```

All dependencies are open-source and compatible with Python 3.x.

---

### Theoretical Framework

ODER models linguistic comprehension as observer-dependent entropy retrieval, not mere prediction error or static syntactic complexity. The governing retrieval law is

```
dS_ret/dτ = γ(τ) [S_max − S_ret(τ)] tanh(τ / τ_char)
```

**Parameters**

* τ\_char — Characteristic retrieval timescale (processing effort)
* γ(τ)   — Observer-dependent retrieval rate
* S\_max  — Maximum retrievable entropy per sentence/trace

**Key Distinctions**

* Retrieval is observer-relative, not purely stimulus-driven.
* Collapse point (τ\_res) aligns with cognitive ERP signatures (N400/P600).
* No reliance on opaque neural embeddings or over-fit baselines.

---

### Simulation Features

**Model Specifications**

* Aurian corpus: synthetic, controlled language for clean complexity manipulation
* Eight stimulus sentences × two observer classes (high/low context)
* Parameterized noise, hierarchical complexity, and observer-class divergence
* Full failure logging and stress-test diagnostics

**Generated Visualizations**

* Entropy-retrieval curves S(τ) by observer and sentence type
* Comparative fit plots for ODER, linear, exponential, and power-law models
* Failure-taxonomy tables with root-cause annotations
* Collapse-token detection, ERP window mapping, and bootstrap confidence intervals
* All plots and tables are written to the `figures/` directory by default

---

### Repository Structure

| File                                | Description                                       |
| ----------------------------------- | ------------------------------------------------- |
| `ODER_Linguistic_Framework.ipynb`   | Main framework reproduction (all paper results)   |
| `ODER_Interactive_Playground.ipynb` | Interactive fitting and falsification environment |
| `requirements.txt`                  | Python dependencies                               |
| `figures/`                          | Output directory for plots and visualizations     |

---

### Extending the Framework

* **Modify corpus** — add new sentences, languages, or observer profiles.
* **Parameter exploration** — probe sensitivity, neurodivergent bands, non-typical observers.
* **Model development** — generalize retrieval law, adapt failure taxonomy.
* **Empirical mapping** — apply to EEG, eye-tracking, or behavioral datasets for in-vivo parameter recovery.

Contributions that improve, stress-test, or generalize the framework are welcome.

---

### Citation

```
Cooper, Evlondo. (2025). Observer-Dependent Entropy Retrieval in Linguistic Computation:  
A Foundational Framework and Benchmarking Methodology.  
https://doi.org/10.5281/zenodo.15428312

Cooper, Evlondo. (2025). ODER modular entropy simulation (Version 1.0) [Software]. Zenodo.  
https://doi.org/10.5281/zenodo.15428312
```

---

### License

**MIT License** — see `LICENSE` for details.

---

### Contact

Evlondo Cooper
[evlocoo@pm.me](mailto:evlocoo@pm.me)
