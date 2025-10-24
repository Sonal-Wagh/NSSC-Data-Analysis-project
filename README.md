# NSSC-Data-Analysis-project: Data Analytics for High-Energy Jet Physics ⚛️

## Project Overview

This project implemented a **hybrid machine learning pipeline** to analyze high-energy jet physics, focusing on both jet classification and the detection of rare or unusual events. The workflow combines classical tabular analysis with deep learning on jet images to create an efficient and scalable analysis tool.

---

## Key Objective

The primary goal was to investigate classificationand anomaly detection in high-energy jet physics data. This involved analyzing a dataset of **53 engineered jet features** and associated **$100 \times 100$ grayscale jet images** to classify the jets and pinpoint anomalous energy distributions.

---

## The Strategic Workflow: Four Key Steps

### 1. Exploratory Data Analysis & Preprocessing

* The dataset was found to be **complete with no missing values**.
* **Standardization** was necessary because feature scales varied significantly due to differences in physical magnitude.

### 2.Dimensionality Reduction

**Principal Component Analysis (PCA)** was applied to the tabular features to capture the principal variance directions.

* **Result:** The **first 10 principal components** captured approximately of the variance.
* **Impact:** PCA reduced the risk of overfitting, provided noise suppression, and led to a faster training speed (approx. 40% less training time) without sacrificing overall accuracy.

### 3. Jet Classification Random Forest

A **Random Forest classifier** was selected as the robust baseline due to its robustness to nonlinear feature interactions and low sensitivity to feature scaling.

* **Performance Highlights:**
    * Accuracy: **0.8055**
    * ROC-AUC: **0.9542** 

### 4. Anomaly Detection and CNN Autoencoder

A **Convolutional Autoencoder (CAE)** was used to reconstruct the jet images and identify anomalies based on the reconstruction error.

* **Method:** Anomalies are identified if the Reconstruction Mean Squared Error (MSE) is greater than the threshold: $\text{MSE} > (\text{mean} + 2\sigma)$.
* **Interpretation:** The autoencoder successfully identified jets with **deviations in morphology**. These anomalies may indicate:
    * **Rare high-energy collisions**
    * Detector noise or instability
    * **Potential signatures beyond Standard Model distributions** 
