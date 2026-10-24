# PCA: World Happiness Reproduction and Fashion-MNIST Application

Author: Karla Hernandez Guerrero  
Course: Data Wrangling (INFOMDW)  
Assignment: Paper Summarization—Data Preparation Report

## Overview

This repository contains the Python notebook accompanying a review of
Greenacre et al.’s (2022) article, *Principal Component Analysis*.

The project reproduces the explained-variance results of the paper’s
World Happiness example and extends the workflow to Fashion-MNIST
to explore dimensionality reduction in fashion-image data.

The analysis uses scikit-learn’s PCA implementation rather than
implementing the algorithm from scratch.

## Repository Contents

- `PCA_Greenacre_FashionMNIST_Reviewed.ipynb`: analysis notebook.
- `figures/`: exported PCA figures.
- `README.md`: project overview and instructions.

## Notebook

The notebook includes:

- Dataset loading and validation.
- Centering and scaling using StandardScaler.
- PCA of five World Happiness indicators across 149 countries.
- Comparison with the paper’s reported explained-variance percentages.
- PCA of 2,000 Fashion-MNIST images, represented by 784 pixel features.
- A 50-component Fashion-MNIST representation.
- A two-dimensional scatterplot colored by clothing category.
- Checks for 80% and 90% cumulative explained variance.
- Export of numerical tables, figures, parameter settings, and
  reproducibility information.

## Figures

The `figures/` folder contains the following outputs:

| File | Description |
|---|---|
| `explained_variance.png` | Individual and cumulative explained variance for World Happiness. |
| `pca_score_plot.png` | World Happiness country scores on the first two principal components. |
| `fashion_pca_scatterplot.png` | Fashion-MNIST scores on the first two principal components, colored by clothing category. |

These files provide larger versions of the figures presented in the
accompanying report. The Fashion-MNIST scatterplot shows component
scores, not reconstructed images.

When the notebook is run, figures and numerical results are saved
to its local `outputs/` folder. The final cell packages these outputs
into a ZIP archive for download. Newly generated files must be
uploaded separately to update the copies in this repository.

## How to Run

1. Download `PCA_Greenacre_FashionMNIST_Reviewed.ipynb`.
2. Open Google Colab: https://colab.research.google.com/
3. Select File → Upload notebook and choose the downloaded file.
4. Run all cells from top to bottom in a fresh runtime.
5. Check that the dataset-loading cells complete without errors.
6. Review the generated tables and figures.
7. Use the final cell to download the results archive.

Internet access is required to retrieve the datasets. The notebook
downloads the World Happiness CSV from the authors’ repository and
retrieves Fashion-MNIST through OpenML.

If the World Happiness download fails, upload
`world-happiness-report-2021.csv` from the authors’ repository to the
Colab working directory, then rerun the loading cell.

## Main Settings

- World Happiness: five indicators, all five components retained.
- Fashion-MNIST: 2,000 images sampled without replacement.
- Image dimensions: 28 × 28 pixels, flattened into 784 features.
- Sampling seed: 42.
- Preprocessing: centering and unit-variance scaling.
- PCA solver: full SVD, without whitening.
- Fashion-MNIST components retained: 50.
- Visualization: first two principal components.
- Variance thresholds: 80% and 90%; Fashion-MNIST thresholds are
  checked only within the fitted 50 components.

## Interpretation and Limitations

The World Happiness comparison checks agreement with the paper’s
reported variance percentages: 47.0% for PC1 and 24.5% for PC2.
It does not establish that every output of the original R analysis
has been reproduced.

Fashion-MNIST is an exploratory extension, not an experiment
reproduced from the paper. Clothing labels are used only to color
the scatterplot; classification accuracy is not evaluated.

The Fashion-MNIST analysis uses one sample, one scaling approach,
and a predefined choice of 50 components. This choice is not claimed
to be optimal. If a variance threshold is not reached within those
50 components, the notebook does not determine the exact number
of additional components required.

The notebook does not include image reconstructions. A fresh,
successful run is needed to verify dataset loading and regenerate
the outputs in the user's environment.

## Data Sources

World Happiness data and original R scripts:
https://github.com/michaelgreenacre/PCA

Fashion-MNIST dataset:
https://github.com/zalandoresearch/fashion-mnist

## References

Greenacre, M., Groenen, P. J. F., Hastie, T., d’Enza, A. I.,
Markos, A., & Tuzhilina, E. (2022). Principal component analysis.
*Nature Reviews Methods Primers*, 2, Article 100.

Xiao, H., Rasul, K., & Vollgraf, R. (2017). Fashion-MNIST:
A novel image dataset for benchmarking machine learning algorithms.
*arXiv:1708.07747*. https://arxiv.org/abs/1708.07747

## AI Assistance

Generative AI was used to assist with code development, debugging,
and editing explanatory text. This assistance does not replace
execution-based validation of the analysis.
