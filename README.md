# Spring 2026 Group Project - Group 2
# Utilizing diverse datasets to improve the efficacy of AI in detection of skin cancer

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Keras](https://img.shields.io/badge/Keras-DeepLearning-red.svg)
![Status](https://img.shields.io/badge/Status-Research%20Project-informational.svg)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow.svg)

---

## Overview
This project explores how dataset diversity impacts the performance of deep learning models for skin cancer detection. Most existing models are trained on predominantly light-skinned datasets, leading to reduced accuracy on darker skin tones.  

We evaluate whether combining the ISIC MILK10 dataset with a synthetic African-focused EHR dataset improves model performance and generalization.

---

## Method

### Model
- EfficientNetB2 (ImageNet pretrained)
- Binary classification: **cancer vs non-cancer**

### Training Strategy
- Transfer learning (freeze → unfreeze)
- Data augmentation:
  - Rescaling
  - Horizontal/vertical flips
- Stratified **80/20 train-validation split**

### Datasets
- **ISIC (MILK10)**: 10,480 dermoscopic images  
- **Synthetic EHR dataset**: 10,015 records (African-focused)

### Tools
- Python
- TensorFlow / Keras
- Google Colab Pro (A100 GPU)

---

## Results

### ISIC-Only Model
- **Accuracy:** 0.8112  
- **AUC:** 0.8839  
- Good generalization  
- Mild overfitting  

### ISIC + EHR Model
- **Accuracy:** 0.8961  
- **AUC:** 0.9642  
- High training performance  
- Significant overfitting  
- Poor generalization  

---

## Key Findings
- Adding synthetic diverse data increased training accuracy but reduced real-world performance.
- Combined datasets introduced **overfitting**, likely due to redundancy or noise.
- Simpler dataset (ISIC-only) generalized better despite lower accuracy.

---

## Limitations
- Binary classification only (no subtype prediction)
- Synthetic data instead of real darker skin images
- No metadata integration
- Custom model limits benchmarking against existing work

---

## Future Work
- Use real, diverse dermatology datasets
- Incorporate metadata (patient demographics, lesion type)
- Expand to **multi-class classification**
- Compare against state-of-the-art dermatology models
- Improve regularization to reduce overfitting

---

## Conclusion
While dataset diversity is essential for equitable AI, simply adding synthetic data is not sufficient. Careful dataset design and model tuning are required to improve both accuracy and generalization across diverse populations.

---

## Authors
- Isis Quinones  
- Beck Petersen
