# Stress-Based Validation of Bio-Inspired Phosphene Vision Encoding

This repository provides reproducibility materials for the manuscript:

**Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding: Trade-Offs among Performance, Safety, and Representation Stability**

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
└── supplementary/
    └── supplementary_materials.pdf
```

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

## Utility Sensitivity Analysis

The utility-weight sensitivity analysis added during revision is provided in:

```text
utility_sensitivity_outputs/Table_Utility_Sensitivity_Weights.csv
utility_sensitivity_outputs/Table_Utility_Sensitivity_Rankings.csv
utility_sensitivity_outputs/Table_Utility_Sensitivity_Scenarios.csv
```

This post-hoc analysis evaluates four operating-preference scenarios:

* Balanced
* Performance-dominant
* Stability-dominant
* Safety-dominant

The analysis was added to examine whether the tri-objective utility ranking depends on the assumed operating preference weights.

## Supplementary Materials

Additional supplementary material is provided in:

```text
supplementary/supplementary_materials.pdf
```

## Access Note

This repository is public and does not require GitHub login for access.

If the GitHub notebook preview does not render properly, the raw notebook can still be downloaded and opened in Google Colab, Jupyter Notebook, or JupyterLab. A static HTML version of the notebook is also provided for direct browser-based inspection.

## Reproducibility Note

The repository provides the analysis notebook, exported benchmark-specific figures and tables, cross-benchmark summary files, and revision-related utility sensitivity outputs. Some analyses may require local path adjustment depending on the execution environment.

