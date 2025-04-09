# 🧠 Advanced SVM Techniques for Imbalanced Spectral Data in BCC Detection

This repository contains code and experiments from my MSc dissertation on **handling class imbalance in Basal Cell Carcinoma (BCC) detection** using Raman spectroscopy data. The project explores and implements advanced **Support Vector Machine (SVM)** strategies to enhance classification performance in highly imbalanced biomedical datasets.

---

## 🩻 Project Overview

Basal Cell Carcinoma is the most common type of skin cancer. In clinical workflows like Mohs Micrographic Surgery, rapid and accurate tumor margin detection is vital. **Multimodal Spectral Histopathology (MSH)** offers a fast, non-invasive solution using Raman spectral data, but presents significant **class imbalance** challenges.

This project systematically evaluates and improves upon a baseline SVM model to better handle such data. Our goal was to **maximize specificity while maintaining sensitivity above 80%**, addressing the real-world need to minimize false positives in cancer diagnosis.

---

## 💡 Techniques Implemented

### 🔧 1. Baseline SVM
- Gaussian RBF & Laplacian kernels
- l2, MinMax, Standard, and Median normalizations
- Threshold tuning via Platt scaling and decision functions
- Cross-validation and full training set thresholding

### 💰 2. Cost-Sensitive SVM
- Penalizes misclassification of the minority class (BCC)
- Class-balanced and tuned penalty ratios
- Achieved up to **93.5% specificity at 80% sensitivity**

### 🌫️ 3. Fuzzy SVM (FSVM)
- Membership values based on:
  - Distance from class centers or estimated hyperplanes
  - Advanced distance metrics: **Mahalanobis**, **Cosine**, **Earth Mover’s Distance**
- Riemannian distance in kernel space for non-linear mappings

### 🌀 4. Kernel Modification
- Adaptive conformal transformation of Gaussian kernels
- Reinforces minority class in the feature space

### 🧪 5. Ensemble SVM
- Multiple SVMs trained on randomly undersampled datasets
- Averaged decision function outputs for final prediction
- Works with cost-sensitive and kernel-modified SVMs

---

## 📊 Evaluation Metrics

- **Sensitivity (Recall)** – % of correctly identified BCC cases
- **Specificity** – % of correctly identified non-BCC cases
- **Partial AUC** – Area under ROC curve for low FPR
- **Specificity @ 80% Sensitivity** – Real-world benchmark for medical relevance

---

## 🧬 Dataset

- Raman spectral data from 152 patient tissue samples
- 23,237 labeled instances
- High imbalance: non-BCC outnumbers BCC
- Train/test split by patient (no data leakage)

---

## 🏁 Key Results

| Model                                  | Sensitivity | Specificity | Sp @ 80% Se |
|---------------------------------------|-------------|-------------|-------------|
| Baseline SVM                          | 83.7%       | 91.1%       | 92.9%       |
| Cost-Sensitive SVM (Tuned)            | 83.7%       | 92.1%       | 93.0%       |
| Kernel-Modified + Cost-Sensitive SVM  | 87.0%       | 91.8%       | **93.5%**   |
| FSVM (Center-Based, Riemann)          | 84.2%       | 92.4%       | 92.8%       |
| Ensemble + Kernel + Cost-Sensitive    | 86.0%       | 91.4%       | 93.0%       |

---

## 🙌 Acknowledgements

Special thanks to **Prof. Ioan Notingher** for his invaluable guidance and support throughout this project.

Gratitude to the research collaborators at the **University of Nottingham** — especially **Alexey Koloydenko**, **Radu Boitor**, and **Peerakarn Jitpukdee** — for their insightful contributions, feedback, and teamwork during the research and implementation phases.
