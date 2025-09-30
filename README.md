## Transistor Anomaly Detection

### 📌 Project Overview
This project implements a PatchCore-style anomaly detection pipeline for transistor image inspection using a pretrained ResNet-50 backbone. The workflow extracts multi-scale features, builds a compact memory bank with PCA and coreset sampling, calibrates thresholds via leave-one-out (LOO), and evaluates anomaly scores on GOOD vs BAD test images.

### 📂 Dataset Composition

[Download Sheet Metal Dataset](https://drive.google.com/file/d/1nBwccjURusxMDT6pibeH2NeBzaVj3wNG/view?usp=drive_link)

- Train set

  - train/good — normal samples

- Test set

  - test/good — normal samples

  - test/bent_lead, test/cut_lead, test/damaged_case, test/misplaced — defect samples (BAD)

### ⚙️ Workflow

Imports & Configurations – environment setup, device, seeds.

Utilities – image loading, preprocessing, normalization.

Backbone Feature Extraction – ResNet-50 (layer2 & layer3 features).

Feature Bank & Thresholding – PCA compression, coreset sampling, FAISS index, LOO τ calibration.

Evaluation – AUROC, AUPRC, Precision, Recall, F1, confusion matrix.

Visualization – anomaly heatmaps, overlays, masks for GOOD and BAD samples.

### 📊 Results

AUROC = 0.900

F1 = 0.880

Precision = 0.970

Recall = 0.800

<img width="904" height="523" alt="image" src="https://github.com/user-attachments/assets/cc02fa53-aa95-4fd2-871c-ac44c3c795b2" />
