# NSSC-Data-Analysis-project: Data Analytics for High-Energy Jet Physics ⚛️

## Project Overview

[cite_start]This project implemented a **hybrid machine learning pipeline** to analyze high-energy jet physics data [cite: 2][cite_start], focusing on both jet classification and the detection of rare or unusual events[cite: 4, 8]. [cite_start]The workflow combines classical tabular analysis with deep learning on jet images to create an efficient and scalable analysis tool[cite: 9, 204].

---

## Key Objective

[cite_start]The primary goal was to investigate **$\underline{\text{classification}}$** and **$\underline{\text{anomaly detection}}$** in high-energy jet physics data[cite: 4]. [cite_start]This involved analyzing a dataset of **53 engineered jet features** and associated **$100 \times 100$ grayscale jet images** [cite: 5, 16, 17] [cite_start]to classify the jets and pinpoint anomalous energy distributions[cite: 4].

---

## The Strategic Workflow: Four Key Steps

### 1. Exploratory Data Analysis & Preprocessing

* [cite_start]The dataset was found to be **complete with no missing values**[cite: 21].
* [cite_start]**Standardization** was necessary because feature scales varied significantly due to differences in physical magnitude[cite: 22].

### 2. $\underline{\text{Dimensionality Reduction (PCA)}}$

[cite_start]**Principal Component Analysis (PCA)** was applied to the tabular features to capture the principal variance directions[cite: 6, 24].

* [cite_start]**Result:** The **first 10 principal components** captured approximately **$\underline{\mathbf{95\% \text{ of the variance}}}$**[cite: 26, 115].
* [cite_start]**Impact:** PCA reduced the risk of overfitting, provided noise suppression, and led to a **$\underline{\text{faster training speed}}$** (approx. 40% less training time) without sacrificing overall accuracy[cite: 7, 29, 31, 115].

### 3. Jet Classification ($\underline{\text{Random Forest}}$)

[cite_start]A **Random Forest classifier** was selected as the robust baseline due to its robustness to nonlinear feature interactions and low sensitivity to feature scaling[cite: 48, 49, 50].

* **Performance Highlights:**
    * [cite_start]Accuracy: **0.8055** [cite: 54]
    * [cite_start]ROC-AUC: **$\underline{\mathbf{0.9542}}$** [cite: 58]

### 4. $\underline{\text{Anomaly Detection}}$ ($\underline{\text{CNN Autoencoder}}$)

[cite_start]A **Convolutional Autoencoder (CAE)** was used to reconstruct the jet images and identify anomalies based on the reconstruction error[cite: 79, 80].

* [cite_start]**Method:** Anomalies are identified if the Reconstruction Mean Squared Error (MSE) is greater than the threshold: $\text{MSE} > (\text{mean} + 2\sigma)$[cite: 86].
* [cite_start]**Interpretation:** The autoencoder successfully identified jets with **deviations in morphology**[cite: 8, 91]. These anomalies may indicate:
    * [cite_start]**$\underline{\text{Rare high-energy collisions}}$** [cite: 92]
    * [cite_start]Detector noise or instability [cite: 93]
    * [cite_start]**$\underline{\text{Potential signatures beyond Standard Model distributions}}$** [cite: 94]
