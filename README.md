# Cancer Type Classification Using RNA-Seq Gene Expression

Dataset: Gene Expression Cancer RNA-Seq from the UCI Machine Learning Repository
Source: https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq

## Overview

This project builds classifiers to distinguish five cancer types (BRCA, KIRC, COAD, LUAD, PRAD) using RNA-Seq gene expression profiles. The dataset contains 801 patient samples and ~20,000 gene expression features.

## Files
- `cancer_ml.ipynb`: Jupyter notebook containing the full analysis and model training.
- `dataset/data.csv`: Gene expression measurements (samples × genes).
- `dataset/labels.csv`: Cancer type labels for samples.

## Pipeline (what was done)

1. Data loading: the notebook reads `dataset/data.csv` and `dataset/labels.csv` into Pandas DataFrames.
2. Cleaning: sample identifier column is removed; labels are extracted from the last column. Missing values are checked.
3. Train-test split: stratified 80/20 split to preserve class proportions.
4. Scaling: features standardized with `StandardScaler`.
5. Dimensionality reduction: `PCA` used to reduce to 100 principal components (large proportion of variance retained).
6. Modeling: three classifiers trained on the PCA-transformed data:
   - Logistic Regression (baseline, `max_iter=2000`)
   - Random Forest (`n_estimators=200`)
   - Support Vector Machine (`kernel='rbf'`)
7. Evaluation: accuracy, confusion matrices, PCA 2D visualization, and 5-fold cross-validation.

## Reported Results (from the notebook)
- Logistic Regression: very high accuracy (notebook reports ~99.84% mean CV accuracy).
- SVM: strong performance (~98.59% mean CV accuracy in notebook).
- Random Forest: strong classification performance on PCA features.

Note: exact numeric performance depends on random state, environment, and the full dataset used; refer to `cancer_ml.ipynb` for the printed outputs.

## How to run

1. Install dependencies listed in `requirements.txt`.
2. Open and run the notebook `cancer_ml.ipynb` in a Python environment (recommend Python 3.8+).

## Author

Dikshya Lamichhane
Kathmandu University
Undergrad student
