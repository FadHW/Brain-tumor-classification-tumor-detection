# Brain Tumor MRI Classification & Detection Project

This project combines MRI image classification and object detection to improve brain tumor analysis using deep learning. It leverages both classification models and a multi-view YOLO-based detection system across MRI anatomical planes.

---

# 1. Brain Tumor Classification

## Dataset
- Kaggle Dataset:  
  https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset  

## Classes
- Glioma  
- Meningioma  
- Pituitary  
- No Tumor  

## Notebook
- Classification Notebook:  
  https://www.kaggle.com/code/fadyhanywadie/classfication  

## Approach
A deep learning image classification model is trained to classify MRI scans into four categories.

### Key Steps
- Data preprocessing and normalization  
- Image augmentation (if applied)  
- CNN-based classification model  
- Training and evaluation on labeled MRI images  

---

# 2. Brain Tumor Detection (YOLO-Based)

## Dataset
- Kaggle Dataset:  
  https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets  

## Notebook
- Detection Notebook:  
  https://www.kaggle.com/code/fadyhanywadie/fork-of-detection-using-yolo-for-brain-tumor   

---

## Project Overview

Brain MRI scans are 3D volumetric data, typically analyzed from three anatomical planes:

### MRI Planes
1. Axial Plane  
   Horizontal slices (top to bottom view)

2. Coronal Plane  
   Vertical slices (front to back view)

3. Sagittal Plane  
   Vertical slices (left to right side view)

---

## Key Idea

Tumors are 3D structures, meaning:
- They may appear clearly in one plane  
- And partially or poorly visible in others  

To solve this, we train separate detection models per plane and combine their predictions.

---

## Technical Architecture

### 1. Data Processing
- Dataset: Brain Tumor Object Detection Dataset (Kaggle)
- Dynamic YAML configuration for Kaggle environment compatibility
- Dataset path automation and cleanup

### Image Augmentation
Using Albumentations:
- Blur  
- Median Blur  
- Grayscale conversion (ToGray)  
- CLAHE (Contrast Limited Adaptive Histogram Equalization)  

These improve generalization and robustness.

---

### 2. Model Training

Three separate YOLO models were trained:

| Plane   | Model Role |
|----------|------------|
| Axial    | Horizontal slice detection |
| Coronal  | Front-to-back detection |
| Sagittal | Side-view detection |

### Training Configuration
- Model: YOLO11s (Ultralytics)
- Image size: 640 × 640
- Epochs: 100
- Hardware: CUDA GPU (Tesla T4)

---

### 3. Weighted Ensemble Inference

To improve reliability, predictions from all models are combined:

| Model   | Weight |
|----------|--------|
| Axial    | 50%    |
| Coronal  | 30%    |
| Sagittal | 20%    |

### Final Decision Rule
A tumor is classified as positive if:

- Weighted confidence score > 0.5

---

## Summary

This project demonstrates a multi-view deep learning system for brain tumor analysis:

- Classification model predicts tumor type  
- YOLO detection models locate tumor regions  
- Multi-plane ensemble improves robustness  

---
