# ODER Linguistic Entropy: Spectral-Admissibility Verification

This repository contains theory-side verification materials for **Observer-Dependent Entropy Retrieval in Linguistic Comprehension: A Bounded-Access Theory of Semantic Timing, Reanalysis, and Collapse**.

This release focuses on the spectral-admissibility verification artifact. The notebook checks one narrow claim: whether the tanh smooth-access baseline used in linguistic ODER leaves a recoverable inverse-gamma signature under finite resolution.

The artifact is synthetic and theory-side; it does not report human empirical validation.

## Canonical Verification Artifact

```text
notebooks/ODER_Linguistic_Spectral_Admissibility_verification_artifact_v1.ipynb
notebooks/ODER_Linguistic_Spectral_Admissibility_verification_artifact_v1.executed.ipynb
```

The source notebook reruns the verification. The executed notebook preserves a completed reference run.

## What the Notebook Verifies

The spectral-admissibility notebook tests whether:

- calibrated bounded saturating alternatives can be separated from the tanh smooth-access baseline;
- the tanh inverse decoder recovers a discriminative gamma profile under finite-resolution noise;
- adversarial Gompertz foils, calibrated to approach the tanh baseline, become confusable only when they move close to tanh below the declared measurement floor;
- trajectory-level RMS deviation, not family label alone, governs finite-resolution distinguishability.

## Verification Report

The current executed artifact reports:

| Check | Result | Status |
| --- | --- | --- |
| Common saturation calibration | maximum absolute deviation from S(3)=0.95 is 6.22e-15 | PASS |
| Primary five-class finite-resolution discriminability | min heteroscedastic accuracy at `sigma=0.04` = 0.855 | PASS |
| Pairwise calibrated-foil discriminability | min tanh-vs-foil accuracy at `sigma=0.04` = 0.940 | PASS |
| Adversarial Gompertz near-equivalence | max deviation = 0.017; RMS = 0.006; noise floor = 0.040 | PASS |
| Classifier robustness under near-equivalent adversarial foil | max classifier accuracy = 0.613 | PASS |
| Trajectory RMS boundary | min accuracy above RMS noise floor = 0.998 | PASS |

The machine-readable report is available at:

```text
outputs/spectral_verification_report.csv
outputs/validation_manifest.json
```

## Repository Layout

```text
ODER-linguistic-entropy/
  README.md
  notebooks/
    ODER_Linguistic_Spectral_Admissibility_verification_artifact_v1.ipynb
    ODER_Linguistic_Spectral_Admissibility_verification_artifact_v1.executed.ipynb
  outputs/
    spectral_calibration_summary.csv
    spectral_noise_scan.csv
    spectral_pairwise_foil_discriminability.csv
    spectral_adversarial_classifier_robustness.csv
    spectral_rms_boundary.csv
    spectral_verification_report.csv
    validation_manifest.json
    figures/
  archive/
    v1.2/
      README.md
  requirements.txt
  environment.yml
  CITATION.cff
  LICENSE
```

## How To Run

Create a clean environment:

```bash
pip install -r requirements.txt
```

Then open:

```text
notebooks/ODER_Linguistic_Spectral_Admissibility_verification_artifact_v1.ipynb
```

Run all cells from the top. The notebook writes verification CSVs, figures, and a manifest into `oder_spectral_outputs/` unless `ODER_SPECTRAL_OUTPUT_ROOT` is set.

## Scope

This repository supports the theory-side spectral-admissibility analysis. It does not provide human-subject validation of linguistic ODER.

The older v1.2 exploratory and benchmarking notebooks are preserved as prior computational materials under `archive/v1.2/`. They are not the canonical verification artifact for this theory-side release.

## License

MIT License. See `LICENSE`.


