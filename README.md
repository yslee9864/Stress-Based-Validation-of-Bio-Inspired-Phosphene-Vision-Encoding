# Stress-Based Validation of Bio-Inspired Phosphene Vision Encoding

This repository provides reproducibility materials for the manuscript:

**Stress-Based Assessment of Bio-Inspired Phosphene Vision Encoding: Trade-Offs among Performance, Safety, and Representation Stability**

## Repository structure

- `notebooks/`: main analysis notebook and static HTML version
- `tables/`: exported tables and CSV summaries
- `figures/`: exported figures used in the manuscript
- `supplementary/`: compressed supplementary results and supporting files

## Main notebook

The main analysis notebook should be provided here:

- `notebooks/RunPackageC_EMNIST_COCO_FullRepro_v2_0407_fixed.ipynb`

If GitHub fails to render the notebook preview, please use one of the following alternatives:

1. Click **Raw** and download the notebook, then open it in Jupyter Notebook, JupyterLab, or Google Colab.
2. View the static HTML version:
   - `notebooks/RunPackageC_EMNIST_COCO_FullRepro_v2_0407_fixed.html`
3. Inspect the generated CSV tables directly in the `tables/` folder.

## Utility sensitivity analysis

The utility-weight sensitivity analysis added during revision is provided in:

- `tables/Table_Utility_Sensitivity_Weights.csv`
- `tables/Table_Utility_Sensitivity_Rankings.csv`
- `tables/Table_Utility_Sensitivity_Scenarios.csv`

This analysis evaluates four operating-preference scenarios:

- Balanced
- Performance-dominant
- Stability-dominant
- Safety-dominant

## Access note

This repository is public and does not require GitHub login for access. If the GitHub notebook preview fails, the raw notebook and static HTML file should still remain accessible.
