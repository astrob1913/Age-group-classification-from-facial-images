#  Age Group Classification from Facial Images

> A Computer Vision project that compares **classical machine learning** and **deep learning** techniques for automatic facial age-group classification.

---

##  Overview

This project implements a complete **Computer Vision pipeline** for **Age Group Classification (AGD)** using facial images.

The objective is to classify a person's face into one of four age groups:

### 1. Child (0–12 years)
### 2. Young (13–33 years)
### 3. Middle-Aged (40–55 years)
### 4. Senior (56+ years)

Three different machine learning approaches were implemented, trained, and compared:

### 1. HOG + Support Vector Machine (SVM)
### 2. HOG + Multi-Layer Perceptron (MLP)
### 3. Convolutional Neural Network (CNN)

The project also includes a real-world **AgeDetection** pipeline that detects faces in a video and predicts their age group.

---

#  Google Drive Resources

The complete project resources are available on Google Drive, including:

*  Original dataset
*  Trained models
*  Demo video for AgeDetection
*  Google Colab notebooks
*  Coursework report

**Google Drive Folder:**

https://drive.google.com/drive/folders/1Kpd5yJWOP55z6wMKD2PhEOx4mpHlN-9-?usp=sharing

> **Note:** Due to GitHub file size limitations, the dataset, trained models (`.pkl`, `.h5`) and intermediate NumPy arrays (`.npy`) are hosted on Google Drive instead of this repository.

---

# Project Highlights

- End-to-end Computer Vision pipeline
- Image preprocessing and feature engineering
- Histogram of Oriented Gradients (HOG) feature extraction
- Hyperparameter tuning using Cross-Validation
- Comparison of Classical ML vs Deep Learning
- Quantitative and qualitative evaluation
- Video-based age group detection
- Google Colab implementation

---

# Dataset

The dataset contains cropped facial images labelled into four age groups.

| Label | Age Group   | Age Range   |
| ----: | ----------- | ----------- |
|     0 | Child       | 0–12 years  |
|     1 | Young       | 13–33 years |
|     2 | Middle-Aged | 40–55 years |
|     3 | Senior      | 56+ years   |

All images were resized to **128 × 128 pixels** before preprocessing.

---

# Methodology

## Data Preprocessing

The following preprocessing steps were applied:

* Resize all images to **128 × 128**
* Parse image labels
* 70/30 Train–Validation split
* Normalize pixel values
* Convert images to grayscale (HOG models)
* Extract HOG descriptors
* Maintain consistent preprocessing across training, validation and testing datasets

---

# Models Implemented

## 1. HOG + SVM

* HOG feature representation
* Hyperparameter tuning using Cross Validation
* Tested:

  * Linear Kernel
  * RBF Kernel
  * C = 1
  * C = 10

### Best Configuration

* **Kernel:** RBF
* **C = 10**

---

## 2. HOG + MLP

* HOG feature representation
* Feedforward Neural Network

Hidden Layers Tested

* (64,)
* (128,)
* (128,64)

Solvers

* Adam
* SGD

### Best Configuration

* **Hidden Layer:** (128,)
* **Solver:** Adam

---

## 3. Convolutional Neural Network (CNN)

Architecture:

* 3 Convolution Layers
* Max Pooling
* Fully Connected Layer
* Softmax Output Layer

Training Strategy

* Adam Optimizer
* Batch Size = 32
* Early Stopping
* Validation Monitoring
* Best model restoration

---

# Performance Comparison

| Model         |  Accuracy | Precision |    Recall |  F1-score |
| ------------- | --------: | --------: | --------: | --------: |
| **HOG + SVM** | **0.775** |     0.771 |     0.775 |     0.772 |
| **HOG + MLP** |     0.738 |     0.736 |     0.738 |     0.736 |
| **CNN**       | **0.780** | **0.781** | **0.780** | **0.775** |

### Key Observation

 **CNN achieved the highest overall performance.**
 **SVM achieved comparable accuracy while being computationally lighter.**
 **MLP produced the lowest performance among the three models.**

---

#  Age Detection on Video

The project also implements an **AgeDetection()** function that:

* Detects faces in a video
* Draws bounding boxes
* Predicts age group for each detected face
* Displays predictions frame-by-frame

---

#  Repository Structure

```text
Age-group-classification-from-facial-images/
│
├── Code/
│   └── CVmain.ipynb
│
├── test_function.ipynb
│
├── README.md
│
├── requirements.txt
│
├── CW PG Report.pdf
│
└── .gitignore
```

> **Note:** Large datasets, trained models and intermediate NumPy arrays are intentionally excluded from this repository to keep it lightweight. The notebook can regenerate these artifacts when the dataset is available.

---

#  Technologies Used

* Python
* OpenCV
* NumPy
* Scikit-learn
* Scikit-image
* TensorFlow / Keras
* Matplotlib
* Joblib
* Google Colab

---

#  Future Improvements

* Transfer Learning (ResNet, EfficientNet, MobileNet)
* Data Augmentation
* Class Imbalance Handling
* Grad-CAM Explainability
* Real-time Webcam Age Detection
* Streamlit Web Application
* Model Deployment using Flask

---

#  Author

**Bhuvanesi Barua**

MSc Data Science
City St George's, University of London

---

#  Acknowledgement

This project was developed as part of a Computer Vision coursework and has been refined into a portfolio project demonstrating both **classical machine learning** and **deep learning** approaches for facial age-group classification.
