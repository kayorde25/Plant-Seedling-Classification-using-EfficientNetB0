# EfficientNetB0 for Multi-Class Plant Seedling Recognition: A Transfer Learning Approach

Deep learning image classification project using EfficientNetB0, transfer learning, and Grad-CAM explainability for plant seedling recognition.

---

## Overview

This project develops a high-performance multi-class image classification model using **EfficientNetB0** and transfer learning to classify plant seedlings into 12 species.

The pipeline is fully reproducible and includes:

- Automated dataset loading from Kaggle  
- Transfer learning + controlled fine-tuning  
- Robust evaluation (classification report, confusion matrix)  
- Model explainability using Grad-CAM  

---

## Problem Statement

Manual identification of plant seedlings is:

- time-consuming  
- error-prone  
- difficult at early growth stages  

This project aims to:

- Build a robust multi-class classification model  
- Leverage pretrained deep learning models  
- Improve prediction interpretability  
- Demonstrate real-world applicability in agriculture  

---

## Why This Matters

Accurate plant classification supports:

- Precision agriculture  
- Early weed detection  
- Crop monitoring systems  
- Automated farming workflows  

This project shows how deep learning can reduce manual effort and improve scalability in agricultural systems.

---

## Dataset

- **Source:** Kaggle  
- **Dataset:** https://www.kaggle.com/datasets/abiolaoolaleye/computer-vision  
- **Samples:** 4,750 images  
- **Classes:** 12 plant species  
- **Original Size:** 128×128×3 → resized to 224×224  

Files:

- `images.npy` → image data  
- `Labels.csv` → class labels  

---

## ⚙️ Reproducibility (IMPORTANT)

This project is fully reproducible.

### Step 1 — Get Kaggle API Key

1. Go to: https://www.kaggle.com/account  
2. Scroll to **API**  
3. Click **Create New API Token**  

---

### Step 2 — Set environment variables

#### Mac / Linux
```bash
export KAGGLE_USERNAME=your_username
export KAGGLE_KEY=your_api_key
