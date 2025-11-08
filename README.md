# Round2_anomaly_detection_nasa
README — NASA/IMS Bearing Anomaly Detection Project
This document provides detailed instructions on how to execute and interpret the anomaly detection pipeline built using the NASA/IMS Bearing dataset. The goal is to automatically identify abnormal patterns in vibration data indicative of bearing degradation or failure.
1. Project Overview The project implements two unsupervised anomaly detection methods: 1. Isolation Forest (statistical tree-based approach) 2. Autoencoder (neural reconstruction-based approach) The code performs: - Data loading and cleaning - Feature engineering (rolling statistics, EWMA, etc.) - Model training and scoring - Visualization and evaluation
2. Dataset Information Dataset: IMS Bearing Data (Set 1) — provided by NSF I/UCR Center for Intelligent Maintenance Systems (IMS) with support from Rexnord Corp. Each file records 1-second vibration signals (20,480 samples) from 8 channels, captured at 20 kHz sampling rate.
4. Prerequisites Install dependencies before running: pip install numpy pandas scikit-learn matplotlib tensorflow
Import os, io, sys, math, warnings Recommended environment: Google Colab or local Jupyter Notebook.
5. How to Run Step 1: Upload the NASA.txt file into Colab or working directory. Step 2: Execute all cells of the notebook anomaly_detection_nasa.ipynb. Step 3: Change output paths from //data/ to local filenames such as: "nasa_anomaly_results.csv”
Step 4: After execution, check the generated CSV and visual outputs.
6. Key Outputs - nasa_anomaly_results.csv — Contains anomaly scores and labels
- Visualization plots — Inline in notebook
7. Interpreting Results - iso_label = 1 indicates anomaly from Isolation Forest - ae_label = 1 indicates anomaly from Autoencoder - proxy_label = 1 identifies statistical outliers (|z| > 3) Higher anomaly counts or reconstruction errors suggest bearing degradation.
