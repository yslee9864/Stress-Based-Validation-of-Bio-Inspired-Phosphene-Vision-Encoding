# Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding

This repository contains the reproducibility materials associated with the revised manuscript:

**Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding: Trade-Offs among Performance, Residual Proxy Safety Burden, and Topology-Based Representation Metrics**

Manuscript ID: `biomimetics-4335630`

## 1. Scope

The repository provides the final fixed-seed notebook and canonical outputs used for the revised manuscript.

The study evaluates four phosphene-vision encoding strategies:

- Rate encoding
- Sparse encoding
- Temporal encoding
- Optimized encoding

The benchmarks are:

- EMNIST Letters
- A reduced four-class COCO-derived image-level classification benchmark

The findings are exploratory, benchmark-specific, and configuration-dependent. They should not be interpreted as clinical validation, implant-user validation, physiological safety validation, or deployment-level robustness evidence.

## 2. Final Reproducibility Notebook

The final notebook is:

`FINAL_REPRO_RunPackageC_EMNIST_COCO_seed0042_20260614.ipynb`

This is the canonical executable notebook associated with the revised manuscript and the uploaded result files.

## 3. Reproducibility Configuration

The final analysis uses the fixed random seed:

`42`

Final run identifier:

`Run_seed0042_20260614_003202`

The manuscript tables, figures, supplementary files, and response materials were regenerated from, or directly verified against, the same final fixed-seed canonical result set.

## 4. Recorded Execution Environment

The final recorded run used:

- Python: `3.12.13`
- Platform: Linux x86_64
- NumPy: `2.0.2`
- pandas: `2.2.2`
- PyTorch: `2.11.0+cpu`
- Device: CPU
- CUDA available: `false`
- Recorded elapsed time: approximately `46.7 minutes`

Runtime may vary depending on the execution environment.

## 5. Recommended Execution Procedure

1. Open `FINAL_REPRO_RunPackageC_EMNIST_COCO_seed0042_20260614.ipynb` in Google Colab or an equivalent Python environment.
2. Use a CPU runtime unless the notebook is deliberately modified.
3. Keep the fixed seed unchanged.
4. Run all cells sequentially.
5. Reuse the saved split indices and fixed-seed configuration.
6. Compare the generated outputs with the canonical files in this repository.

## 6. Repository Structure

```text
.
├── README.md
├── FINAL_REPRO_RunPackageC_EMNIST_COCO_seed0042_20260614.ipynb
├── coco_4cls/
│   ├── figures/
│   ├── models/
│   ├── raw/
│   ├── tables/
│   ├── BenchmarkSeed.json
│   └── benchmark_summary.json
├── emnist_letters/
│   ├── figures/
│   ├── models/
│   ├── raw/
│   ├── tables/
│   ├── BenchmarkSeed.json
│   └── benchmark_summary.json
├── reviewer2_comment_outputs/
│   ├── comment1_coco_diagnostic_metrics/
│   ├── comment2_uncertainty_bootstrap_CI/
│   ├── comment3_pareto_dominance/
│   ├── comment3_pareto_frontier/
│   └── comment4_weight_sensitivity/
└── summary/
    ├── Config_Benchmarks.json
    ├── CrossBenchmark_TriObjective_Summary.csv
    ├── RunManifest.json
    └── SanityCheck_Artifacts.csv
```

## 7. Manuscript-to-File Mapping

### COCO-derived diagnostic analysis

| Manuscript item | Supporting file |
|---|---|
| Table 5.1a | `reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/Manuscript_Table_COCO_Diagnostic_Metrics.csv` |
| Table 5.1b | `reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_rate.csv` |
| Table 5.1b | `reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_sparse.csv` |
| Table 5.1b | `reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_temporal.csv` |
| Table 5.1b | `reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_optim.csv` |
| Table 5.1c | Encoder-specific `COCO_confusion_matrix_*.csv` and `COCO_confusion_matrix_*.png` files in the same folder |

Table 5.1a reports accuracy, balanced accuracy, macro-F1, the four-class chance baseline, and the accuracy-minus-chance margin.

### Tri-objective and uncertainty analyses

| Manuscript item | Supporting file |
|---|---|
| Table 5.5 | `summary/CrossBenchmark_TriObjective_Summary.csv` |
| Table 5.5a | `reviewer2_comment_outputs/comment2_uncertainty_bootstrap_CI/Manuscript_Table_Utility_ConditionBootstrap_CI.csv` |
| Table 5.6 | `reviewer2_comment_outputs/comment4_weight_sensitivity/Manuscript_Table_Utility_WeightSensitivity.csv` |
| Figure 5.8 | `reviewer2_comment_outputs/comment3_pareto_frontier/Manuscript_Table_Pareto_Frontier.csv` |
| Table 5.6a | `reviewer2_comment_outputs/comment3_pareto_dominance/Manuscript_Table_Pareto_Dominance.csv` |

The condition-level bootstrap analysis uses 5000 percentile-bootstrap resamples over the non-clean encoder–operator–level rows.

Pareto-front membership and pairwise dominance were computed from the original unnormalized tri-objective values. Normalized values were used only for visualization.

### Methods and condition-level outputs

| Content | Supporting files |
|---|---|
| Benchmark configuration, stress operators, and sweep levels | `emnist_letters/tables/Table4_1_BenchmarkConfig.csv`; `coco_4cls/tables/Table4_1_BenchmarkConfig.csv` |
| Residual proxy severity definitions | `emnist_letters/tables/Table2_SafetyConstraints_SeverityDefinitions.csv`; `coco_4cls/tables/Table2_SafetyConstraints_SeverityDefinitions.csv` |
| Condition-wise performance and residual proxy safety-burden metrics | `emnist_letters/tables/TableStress_PerfSafety_ByEncoderOpLevel.csv`; `coco_4cls/tables/TableStress_PerfSafety_ByEncoderOpLevel.csv` |

The original program-generated filenames were retained to preserve traceability between notebook outputs, supplementary files, manuscript tables, and response materials.

## 8. Interpretation Notes

### COCO-derived benchmark

The reduced four-class COCO-derived benchmark operates in a low-performance, narrow-margin discrimination regime. Encoder preferences should therefore be interpreted only within this restricted diagnostic setting, not as evidence of robust natural-scene understanding.

### Fixed-decoder configuration

A benchmark-specific decoder was trained using pooled clean percepts from the four encoders and then held fixed during stress evaluation. This reduces variation from repeated decoder retraining but does not disentangle encoder-induced effects from decoder sensitivity.

The reported findings therefore represent configuration-dependent joint encoder–decoder responses rather than encoder-only robustness measurements.

### Topology-based representation metric

The implementation label `TSI` is retained in some exported files for compatibility with the analysis pipeline. In the manuscript, it is interpreted as a normalized topology-based representation diagnostic or metric within the evaluated configuration, not as a validated general measure of representational stability.

### Residual proxy safety burden

The safety-related quantity is a residual proxy safety burden based on post-projection constraint violations. It is not a physiological, electrochemical, clinical, or implant safety measurement.

### Stochastic stress exploration

The fuzzing-related outputs are exploratory stress-sampling artifacts from the final fixed-seed pipeline. They should not be interpreted as exhaustive multi-operator testing, cross-benchmark deployment validation, or deployment-level operating-envelope characterization.

## 9. Data Availability

EMNIST and COCO are publicly available benchmark datasets and remain subject to their respective licenses and terms of use.

This repository does not redistribute source benchmark images unless redistribution is permitted under the applicable dataset license.
datasets remain subject to their respective licenses.
