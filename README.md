# NSSC-Data-Analysis-project
**Project Overview: Data Analytics for High-Energy Jet Physics**
This project applies a hybrid machine learning pipeline to high-energy jet physics data for classification and anomaly detection. The workflow combines classical tabular analysis with deep learning on jet image representations to create an efficient and scalable analysis tool.
**Objective:**
The primary objective of this project was to investigate classification and anomaly detection in high-energy jet physics data. This involved analyzing a dataset of engineered jet features and associated jet images to classify the jets and identify anomalous energy distributions
**Workflow**
**1.Exploratory Data Analysis & Preprocessing:** The dataset, containing 53 engineered tabular jet features and $100 \times 100$ jet images, was analyzed3333. The data was found to be complete, but standardization was required due to significant differences in feature scales4.
**2.Dimensionality Reduction:** Principal Component Analysis (PCA) was applied to the tabular features to capture principal variance directions.
Result: The first 10 principal components captured approximately 95% of the variance, which reduced noise and improved training efficiency without degrading model performance.
**3.Jet Classification:** A Random Forest classifier was used for tabular prediction.
Performance: The model achieved an Accuracy of 0.8055 and an ROC-AUC of 0.9542.
**4.Anomaly Detection:** An **autoencoder-based system (a Convolutional Autoencoder)** was used for anomaly detection on the image data
Method: The autoencoder reconstructs jet images, and anomalies are identified if the reconstruction Mean Squared Error (MSE) is greater than the threshold $(\text{mean} + 2\sigma)$10101010.
Interpretation: The autoencoder successfully identified deviations in jet morphology that may correspond to rare physics events, detector noise, or potential signatures beyond the Standard Model distributions.
