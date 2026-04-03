# EfficientNetB0 for Multi-Class Plant Seedling Recognition: A Transfer Learning Approach

Deep learning image classification project using EfficientNetB0, transfer learning, and Grad-CAM explainability for plant seedling recognition.

---

## Overview

This project develops a multi-class image classification model using **EfficientNetB0** and transfer learning to classify plant seedlings into 12 species.

The workflow includes:

- Loading dataset files from a Kaggle-mounted input directory
- Label encoding and stratified train/validation/test split
- Transfer learning with EfficientNetB0
- Controlled fine-tuning
- Evaluation with classification report and confusion matrix
- Explainability using Grad-CAM

---

## Problem Statement

Manual identification of plant seedlings is time-consuming and error-prone, especially in early growth stages where visual differences between species are subtle.

This project aims to:

- Build a robust multi-class classification model
- Leverage pretrained deep learning architectures
- Evaluate performance across multiple plant species
- Improve interpretability using explainable AI techniques

---

## Why This Matters

Accurate plant seedling classification has practical applications in:

- precision agriculture
- early weed detection
- crop monitoring
- automated agricultural workflows

A reliable image classification model can reduce manual inspection effort, improve crop management efficiency, and support scalable agricultural technologies.

---

## Dataset

- **Source:** Kaggle
- **Dataset:** `abiolaoolaleye/computer-vision`
- **Link:** https://www.kaggle.com/datasets/abiolaoolaleye/computer-vision
- **Samples:** 4,750 images
- **Classes:** 12 plant species
- **Original Image Size:** 128 × 128 × 3
- **Model Input Size:** 224 × 224 × 3

Dataset files:

- `images.npy` — image array
- `Labels.csv` — class labels

---

## Dataset Access

This project is designed to run inside a **Kaggle Notebook** or another environment where the dataset is already available locally.

The code detects the execution environment automatically:

- In **Kaggle**, it loads from:
  ```python
  /kaggle/input/computer-vision
