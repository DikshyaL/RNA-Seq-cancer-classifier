# Cancer Type Classification Using RNA-Seq Gene Expression Data

## Overview

This project applies machine learning techniques to classify five cancer types using high-dimensional RNA-Seq gene expression data. The dataset contains 801 samples and 20,531 gene expression features. Due to the high dimensionality, dimensionality reduction techniques and explainable AI methods are used to analyze structure, visualize class separability, and interpret model predictions.

The goal is to build a robust and interpretable machine learning pipeline for cancer classification using gene expression patterns.

---

## Dataset Description

This study uses the Gene Expression Cancer RNA-Seq dataset from the UCI Machine Learning Repository.

Source: https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq

Citation:
Fiorini, S. (2016). gene expression cancer RNA-Seq [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5R88H.

The dataset is derived from The Cancer Genome Atlas (TCGA) RNA-Seq project.

### Dataset Characteristics

- 801 patient samples
- 20,531 gene expression features
- 5 cancer types:
  - BRCA (Breast Cancer)
  - KIRC (Kidney Renal Clear Cell Carcinoma)
  - COAD (Colon Adenocarcinoma)
  - LUAD (Lung Adenocarcinoma)
  - PRAD (Prostate Adenocarcinoma)

### Data Format

- Rows represent patient samples
- Columns represent gene expression features
- Features are anonymized (gene_0 to gene_20530)
- Values represent normalized RNA-Seq expression levels

---

## Objectives

- Classify cancer types using gene expression data
- Handle high-dimensional feature space efficiently
- Apply dimensionality reduction techniques (PCA, t-SNE, UMAP)
- Train and compare multiple machine learning models
- Interpret model decisions using feature importance and SHAP
- Visualize biological clustering patterns in reduced space

---

## Workflow

1. Data loading and preprocessing  
2. Data cleaning and normalization  
3. Train-test split with stratification  
4. Feature scaling using StandardScaler  
5. Dimensionality reduction using PCA  
6. Visualization using t-SNE and UMAP  
7. Model training and evaluation  
8. Feature importance analysis  
9. Model explainability using SHAP  

---

## Dimensionality Reduction

### PCA
Used to reduce dimensionality while preserving global variance.

### t-SNE
Used to visualize local structure and clustering patterns in gene expression space.

### UMAP
Used to preserve both local and global structure, producing clearer biological clustering.

Observation:
- PCA shows weak separability
- t-SNE and UMAP show strong clustering of cancer types

---

## Machine Learning Models

The following models were used:

- Logistic Regression (baseline)
- Random Forest Classifier
- Support Vector Machine (SVM with RBF kernel)

---

## Evaluation Metrics

- Accuracy score
- Confusion matrix
- 5-fold cross-validation

Results show:
- SVM and Logistic Regression perform strongly
- Random Forest provides robust feature-based learning
- Low variance across cross-validation folds indicates model stability

---

## Explainability

### Feature Importance (Random Forest)

Random Forest is trained on original scaled gene expression data to identify influential features contributing to classification.

### SHAP (SHapley Additive Explanations)

SHAP is used to interpret model predictions at both global and local levels.

- Global interpretation: identifies most important features overall
- Local interpretation: explains individual predictions

Note:
Since gene identifiers are anonymized (gene_0 to gene_20530), importance refers to predictive features rather than biological gene names.

---

## Key Insights

- Gene expression data contains strong non-linear structure
- Linear methods (PCA) are insufficient for clear separation
- Non-linear embeddings (t-SNE, UMAP) reveal distinct clustering
- Machine learning models achieve high classification accuracy
- Explainable AI improves interpretability of predictions

---

## Technologies Used

- Python
- NumPy, Pandas
- Scikit-learn
- Matplotlib, Seaborn
- UMAP-learn
- SHAP

---

## Results Summary

- High classification accuracy achieved across models
- SVM performed best in most cases
- UMAP provided best visualization separation
- SHAP improved model interpretability
- Random Forest identified key predictive features

---

## Conclusion

This project demonstrates that machine learning techniques can effectively classify cancer types using high-dimensional gene expression data. The combination of dimensionality reduction, classification models, and explainable AI provides both high performance and interpretability.

While PCA provides limited separability, t-SNE and UMAP reveal strong underlying structure in the dataset. SHAP analysis further enhances transparency by explaining model decisions.

Overall, this work highlights the power of combining machine learning and visualization techniques for biomedical data analysis.

---

## Author

Dikshya Lamichhane  
Computer Engineering Student  
Kathmandu University

---

## Note

This project is for educational and research demonstration purposes using publicly available anonymized gene expression data.
