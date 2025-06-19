# Breast Cancer Clustering Analysis with PCA, K-Means and HCA

This repository contains an end-to-end analysis of the Wisconsin Diagnostic Breast Cancer (WDBC) dataset. The goal is to explore the structure of the data, apply different normalization methods, perform dimensionality reduction using Principal Component Analysis (PCA), and finally cluster the data using both **K-Means** and **Hierarchical Clustering** (HCA). The performance of the clustering is validated using internal and external metrics.

## 📁 Dataset

The dataset used is `wdbc.data` from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)). It contains 569 samples and 32 columns:
- Column 0: ID (discarded)
- Column 1: Diagnosis label (M = malignant, B = benign)
- Columns 2-31: 30 real-valued features computed from digitized images of a breast mass.

## 🔍 Project Structure

### 1. Data Preprocessing
- Load the data without headers.
- Identify label and feature columns.
- Check for missing values and data types.

### 2. Exploratory Data Analysis (EDA)
- Histograms and scatter plots to understand the distribution of features.
- Compute basic statistics and check for skewness and variability.

### 3. Normalization
Three different normalization methods were applied:
- **Min-Max Scaling**
- **Logarithmic Normalization**
- **Standard Scaling**

### 4. Dimensionality Reduction
- **PCA** applied to each normalization method.
- Explained variance plots are used to choose the optimal number of components.
- Best results obtained with Log or MinMax scaling, using 6 principal components.

### 5. Clustering
- **K-Means Clustering**: Number of clusters selected using the Elbow method and internal validation metrics (Silhouette, Davies-Bouldin, Calinski-Harabasz).
- **Hierarchical Clustering (HCA)**: Tested using Ward, Complete, Average, and Single linkages. Dendrograms and internal metrics guide the evaluation.

### 6. Validation
- **Internal Metrics**: Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz Index.
- **External Metrics**: Accuracy and Adjusted Rand Index (ARI) compared against the true labels.
- **Visualization**: PCA plots with ground-truth and predicted cluster labels.

## ✅ Results

- **Best clustering performance**: K-Means with 2 clusters using PCA-reduced Log-scaled data.
- **Accuracy**:
