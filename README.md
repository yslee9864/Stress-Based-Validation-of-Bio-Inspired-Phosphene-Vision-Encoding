# Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding

This repository provides reproducibility materials for the manuscript:

**Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding: Trade-Offs among Performance, Safety, and Representation Stability**

---

## Repository Structure

```text
.
├── README.md
├── notebooks/
│   ├── RunPackageC_EMNIST_COCO_FullRepro_v2_0407.ipynb
│   └── RunPackageC_EMNIST_COCO_FullRepro_v2_0407.html
├── emnist_letters_figure_model_table/
│   ├── figures/
│   ├── models/
│   ├── tables/
│   └── benchmark_summary.json
├── coco_4cls_figure_model_table/
│   ├── figures/
│   ├── models/
│   ├── tables/
│   └── benchmark_summary.json
├── summary/
│   ├── CrossBenchmark_TriObjective_Summary.csv
│   └── SanityCheck_Artifacts.csv
├── utility_sensitivity_outputs/
│   ├── Table_Utility_Sensitivity_Weights.csv
│   ├── Table_Utility_Sensitivity_Rankings.csv
│   └── Table_Utility_Sensitivity_Scenarios.csv
├── reviewer2_comment_outputs/
│   ├── comment1_coco_diagnostic_metrics/
│   ├── comment2_uncertainty_bootstrap_CI/
│   └── comment3_pareto_dominance/
└── supplementary/
    ├── supplementary_materials.pdf
    ├── Supplementary_Figure_S1_OperatorWise_Accuracy.png
    ├── Supplementary_Figure_S2_OperatorWise_Severity.png
    └── Supplementary_Figure_S3_OperatorWise_TSI.png
```

---

## Main Notebook

The original executable notebook is provided in:

```text
notebooks/RunPackageC_EMNIST_COCO_FullRepro_v2_0407.ipynb
```

This notebook is retained as the original executable analysis file used for the manuscript-level experiments.

If GitHub fails to render the `.ipynb` notebook preview because of notebook metadata or renderer limitations, please use one of the following alternatives:

1. Click **Raw** and download the notebook, then open it in Google Colab, Jupyter Notebook, or JupyterLab.
2. View the static HTML version:

```text
notebooks/RunPackageC_EMNIST_COCO_FullRepro_v2_0407.html
```

The HTML file is provided as a browser-accessible fallback for inspection without relying on GitHub’s notebook renderer.

---

## Benchmark-Specific Results

Benchmark-specific figures, tables, trained model artifacts, and summary files are organized separately for the two evaluated benchmarks.

### EMNIST Letters

```text
emnist_letters_figure_model_table/
├── figures/
├── models/
├── tables/
└── benchmark_summary.json
```

This folder contains the exported artifacts for the EMNIST Letters symbolic-recognition benchmark.

### Reduced Four-Class COCO-Derived Benchmark

```text
coco_4cls_figure_model_table/
├── figures/
├── models/
├── tables/
└── benchmark_summary.json
```

This folder contains the exported artifacts for the reduced four-class COCO-derived image-level classification benchmark.

---

## Cross-Benchmark Summary

Cross-benchmark summary files are provided in:

```text
summary/
```

Key files include:

```text
summary/CrossBenchmark_TriObjective_Summary.csv
summary/SanityCheck_Artifacts.csv
```

These files summarize benchmark-level comparisons and artifact-generation checks.

---

## Utility Sensitivity Analysis

The utility-weight sensitivity analysis added during revision is provided in:

```text
utility_sensitivity_outputs/Table_Utility_Sensitivity_Weights.csv
utility_sensitivity_outputs/Table_Utility_Sensitivity_Rankings.csv
utility_sensitivity_outputs/Table_Utility_Sensitivity_Scenarios.csv
```

This post-hoc analysis evaluates four operating-preference scenarios:

- Balanced
- Performance-dominant
- Stability-dominant
- Safety-dominant

The analysis was added to examine whether the tri-objective utility ranking depends on the assumed operating preference weights.

---

## Reviewer 2 Comment Outputs

Additional experimental outputs generated in response to Reviewer 2's comments are provided in:

```text
reviewer2_comment_outputs/
├── comment1_coco_diagnostic_metrics/
├── comment2_uncertainty_bootstrap_CI/
└── comment3_pareto_dominance/
```

These outputs correspond directly to the additional analyses added during revision.

### Comment 1: COCO-Derived Diagnostic Metrics

Reviewer 2 requested additional diagnostic metrics for the reduced four-class COCO-derived benchmark, including balanced accuracy, macro-F1, per-class precision, per-class recall, per-class F1-score, and confusion matrices.

The corresponding outputs are provided in:

```text
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/
```

Key files include:

```text
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/Manuscript_Table_COCO_Diagnostic_Metrics.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_rate.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_sparse.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_temporal.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_optim.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_rate.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_sparse.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_temporal.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_classification_report_optim.csv
```

Confusion-matrix figures are also provided:

```text
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_rate.png
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_sparse.png
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_temporal.png
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_confusion_matrix_optim.png
```

Clean-condition prediction files are included for traceability:

```text
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_clean_predictions_rate.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_clean_predictions_sparse.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_clean_predictions_temporal.csv
reviewer2_comment_outputs/comment1_coco_diagnostic_metrics/COCO_clean_predictions_optim.csv
```

### Comment 2: Statistical Uncertainty and Bootstrap Confidence Intervals

Reviewer 2 requested uncertainty estimates for accuracy and tri-objective utility values.

The corresponding outputs are provided in:

```text
reviewer2_comment_outputs/comment2_uncertainty_bootstrap_CI/
```

Key files include:

```text
reviewer2_comment_outputs/comment2_uncertainty_bootstrap_CI/Accuracy_Wilson_CI_ByEncoderOpLevel.csv
reviewer2_comment_outputs/comment2_uncertainty_bootstrap_CI/Manuscript_Table_Utility_ConditionBootstrap_CI.csv
```

The utility confidence intervals were computed using a condition-level percentile bootstrap over the non-clean encoder–operator–level rows. Accuracy confidence intervals were estimated using Wilson binomial confidence intervals.

### Comment 3: Pareto-Style Dominance Analysis

Reviewer 2 requested additional multi-objective decision analysis beyond weighted utility values.

The corresponding output is provided in:

```text
reviewer2_comment_outputs/comment3_pareto_dominance/
```

Key file:

```text
reviewer2_comment_outputs/comment3_pareto_dominance/Manuscript_Table_Pareto_Dominance.csv
```

This table reports a Pareto-style dominance summary across the three stress-integrated objective axes:

- `TSI_P`: stress-integrated functional performance, treated as a maximization objective
- `TSI_R`: stress-integrated topology-based representation metric, treated as a maximization objective
- `R_safe`: integrated residual proxy safety burden, treated as a minimization objective

An encoder was considered dominated if another encoder achieved equal or better values on all three axes and a strictly better value on at least one axis.

---

## Supplementary Materials

Additional supplementary material is provided in:

```text
supplementary/supplementary_materials.pdf
```

Supplementary figures are provided as:

```text
supplementary/Supplementary_Figure_S1_OperatorWise_Accuracy.png
supplementary/Supplementary_Figure_S2_OperatorWise_Severity.png
supplementary/Supplementary_Figure_S3_OperatorWise_TSI.png
```

These supplementary figures provide operator-wise accuracy, residual severity, and topology-based representation metric trajectories.

---

## Access Note

This repository is public and does not require GitHub login for access.

If the GitHub notebook preview does not render properly, the raw notebook can still be downloaded and opened in Google Colab, Jupyter Notebook, or JupyterLab. A static HTML version of the notebook is also provided for direct browser-based inspection.

---

## Reproducibility Note

The repository provides:

- the final executable analysis notebook,
- a static HTML version of the notebook,
- benchmark-specific figures, tables, trained model artifacts, and summary files,
- cross-benchmark summary files,
- utility sensitivity analysis outputs,
- additional experimental outputs generated in response to Reviewer 2,
- supplementary materials and supplementary figures.

All major manuscript-level results were generated from the final execution notebook. Some analyses may require local path adjustment depending on the execution environment.

The framework should be interpreted as a simulation-based assessment pipeline under simplified SPV conditions rather than as a clinically or physiologically calibrated prosthetic-vision validation environment.

---

## Data Note

The experiments use publicly available benchmark datasets, including EMNIST Letters and MS COCO-derived image-level samples. Original dataset files are not redistributed in this repository. Users should obtain the original datasets from their respective official sources and licenses if full re-execution is required.

The repository provides exported artifacts, result tables, figures, and revision-related diagnostic outputs generated from the final experimental run.

---

## License

Please refer to the repository license file for usage terms. Original datasets remain subject to their respective licenses.
