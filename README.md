# EfficientNetB0 for Multi-Class Plant Seedling Recognition: A Transfer Learning Approach

Deep learning image classification project using EfficientNetB0, transfer learning, and explainability (Grad-CAM) for plant seedling recognition.

---

## Overview

Accurate classification of plant seedlings is an important problem in precision agriculture, enabling early weed detection, crop monitoring, and automated decision-making systems.

This project develops a high-performance image classification model using **EfficientNetB0** and transfer learning to classify plant seedlings into multiple categories. The model is trained on a curated dataset of plant images and evaluated using standard classification metrics.

In addition, **Grad-CAM visualization** is used to improve model interpretability and demonstrate how the model makes predictions.

---

## Problem Statement

Manual identification of plant seedlings is time-consuming and error-prone, especially in early growth stages where visual differences are subtle.

The objective of this project is to:

* Build a robust multi-class image classification model
* Leverage pretrained deep learning architectures for improved performance
* Evaluate classification performance across multiple plant species
* Improve interpretability using explainable AI techniques

---

## Dataset

* **Source:** Kaggle
* **Dataset:** Plant Seedling Classification
* **Samples:** 4,750 images
* **Classes:** 12 plant species
* **Image size:** 128 × 128 × 3 (resized to 224 × 224 for EfficientNet)

The dataset was stored as:

* `images.npy` (image array)
* `Labels.csv` (class labels)

---

## Methodology

### 1. Data Preparation

* Loaded dataset from Kaggle environment
* Encoded categorical labels using LabelEncoder
* Converted labels to one-hot encoding
* Applied reproducible train/validation/test split

### 2. Preprocessing

* Resized images from 128×128 → 224×224
* Applied EfficientNet preprocessing
* Ensured compatibility with pretrained ImageNet weights

### 3. Model Architecture

* **Base model:** EfficientNetB0 (pretrained on ImageNet)
* Frozen convolutional base (transfer learning stage)
* Custom classification head:

  * GlobalAveragePooling
  * BatchNormalization
  * Dense layer (ReLU)
  * Dropout (0.4)
  * Softmax output layer

### 4. Training Strategy

* Stage 1: Feature extraction (frozen backbone)
* Stage 2: Fine-tuning (limited layer unfreezing)
* Callbacks:

  * EarlyStopping
  * ReduceLROnPlateau
  * ModelCheckpoint

### 5. Evaluation

* Accuracy and loss tracking
* Classification report (precision, recall, F1-score)
* Confusion matrix
* Test set evaluation

### 6. Explainability (Grad-CAM)

* Visualized activation maps
* Identified regions influencing predictions
* Improved trust and interpretability

---

## Results

| Metric                     | Value           |
| -------------------------- | --------------- |
| Validation Accuracy (Best) | ~89–90%         |
| Test Accuracy              | ~0.89 (approx.) |
| Number of Classes          | 12              |
| Dataset Size               | 4,750 images    |

Key observations:

* Transfer learning delivered strong performance quickly
* Fine-tuning did not significantly improve accuracy
* Model generalized well across most classes

---

## Model Selection Rationale

EfficientNetB0 was selected due to its strong performance-to-efficiency ratio. It provides high accuracy with fewer parameters compared to traditional CNN architectures.

Transfer learning was highly effective for this dataset, as pretrained ImageNet features generalized well to plant images.

Fine-tuning was explored but resulted in slight performance degradation, likely due to:

* limited dataset size
* overfitting
* instability in deeper layers

Therefore, the final model was selected from the transfer learning stage.

---

## Explainability with Grad-CAM

Grad-CAM was applied to visualize which regions of the image influenced model predictions.

This allows:

* validation of model behavior
* detection of spurious correlations
* improved interpretability for real-world applications

The model consistently focused on relevant plant structures, indicating meaningful feature learning.

---

## Limitations

* Dataset size is relatively small for deep learning
* Original image resolution required upscaling
* Fine-tuning was sensitive to hyperparameters
* No external validation dataset used

---

## Future Improvements

* Compare with EfficientNetB1–B3 and MobileNetV3
* Apply stronger data augmentation
* Use k-fold cross-validation
* Deploy model via Streamlit or FastAPI
* Optimize for edge deployment (mobile/IoT)

---

## Tech Stack

* Python
* TensorFlow / Keras
* NumPy, Pandas
* Scikit-learn
* Matplotlib

---

## Project Structure

```
├── data/
├── notebook.ipynb
├── README.md
├── requirements.txt
└── outputs/
```

---

## Reproducibility

To reproduce this project:

1. Download dataset from Kaggle:
   https://www.kaggle.com/datasets/abiolaoolaleye/computer-vision

2. Place dataset in Kaggle or local environment

3. Run notebook from top to bottom

4. Ensure dependencies are installed:

```
pip install -r requirements.txt
```

---

## Key Insights

* Transfer learning is highly effective for small-to-medium image datasets
* EfficientNet provides strong performance with minimal tuning
* Fine-tuning must be carefully controlled to avoid overfitting
* Explainability techniques improve model trust and usability

---

## Author

Abiola Olaleye

---

## License

This project is for educational and portfolio purposes.
##EfficientNetB0 for Multi-Class Plant Seedling Recognition: A Transfer Learning Approach


Deep learning image classification project using transfer learning, fine-tuning, and explainability (Grad-CAM).
