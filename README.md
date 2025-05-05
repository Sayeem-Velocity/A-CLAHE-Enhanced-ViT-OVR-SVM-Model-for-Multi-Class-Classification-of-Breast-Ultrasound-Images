Here's a clean, professional, and user-friendly version you can directly use in your GitHub `README.md`:

---

# A CLAHE-Enhanced ViT OVR-SVM Model for Multi-Class Classification of Breast Ultrasound Images

**Dataset**: [Breast Ultrasound Images Dataset – Kaggle](https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset)

## 📌 Overview

This project presents a robust hybrid pipeline for classifying breast cancer using ultrasound images, addressing challenges like low contrast, class imbalance, and imaging variability. A Vision Transformer (ViT) is combined with a One-vs-Rest Support Vector Machine (OVR-SVM) to achieve high-accuracy predictions across three classes: **benign**, **malignant**, and **normal**.

---

## 🗂 Dataset Summary

* **Original Samples**: 789 images

  * Benign: 445
  * Malignant: 211
  * Normal: 133
* **Filtered**: Only unmasked, high-quality images retained
* **Balanced Dataset**: 1000 images per class using oversampling
* **Split**:

  * Train: 70%
  * Validation: 10%
  * Test: 20%

---

## 🛠 Preprocessing Pipeline

1. **Resizing**: All images resized to `224×224` pixels
2. **CLAHE**: Contrast Limited Adaptive Histogram Equalization applied to improve feature visibility
3. **Class Balancing**: Performed post-CLAHE with oversampling to ensure uniformity across all classes

---

## 🔍 Feature Extraction – Vision Transformer (ViT)

* **Patch Size**: 8
* **Embedding Dim**: 48
* **Transformer Layers**: 1
* **Transformer Units**: \[128, 64]
* **MLP Head**: \[4096, 2048]
* **Dropout**: 0.1
* **Input Shape**: `3×224×224`
* ViT was used **only for feature extraction** (frozen weights)

---

## 🧠 Classification – One-vs-Rest SVM

* **Classifier**: One-vs-Rest SVM with RBF Kernel
* **Input**: Standardized ViT features
* **Epochs**: 25
* **Purpose**: Handle multi-class classification with strong generalization

---

## 📊 Evaluation Results

**Validation Set**:

* Accuracy: **98.67%**
* F1 Score: **0.9867**
* Precision: **0.9867**
* Recall: **0.9867**

**Test Set**:

* Accuracy: **98.83%**
* Excellent performance confirmed via confusion matrix with minimal misclassifications

---

## ✅ Highlights

* 💡 CLAHE improves contrast in complex tissue textures
* 🧠 ViT captures fine-grained spatial features
* ⚙️ SVM provides strong decision boundaries and generalization
* 📈 Outperforms conventional CNN-based models in accuracy and consistency

---

> ⚠️ **Note**: Only **real, unmasked ultrasound images** were used in this study. No artificially masked or low-quality samples were included.
