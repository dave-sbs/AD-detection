# Classifying Dementia in Brain MRI Scans with Convolutional Neural Networks

This project leverages Convolutional Neural Networks (CNNs) to detect signs of dementia in brain MRI scans. The goal is to provide an early detection tool that can assist clinicians in identifying dementia in its early stages, aiding in timely interventions.

## Table of Contents

1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Data Preprocessing](#data-preprocessing)
4. [Binary Classification](#binary-classification)
5. [Our Models](#our-models)
6. [Discussion](#discussion)
7. [Limitations](#limitations)
8. [Conclusion](#conclusion)
9. [Citations](#citations)

---

## Introduction

Alzheimer's disease, a leading cause of dementia, affects millions of people globally. The project's aim is to develop a model that can classify brain MRI scans into "Dementia" or "Non-Demented" categories using a CNN, assisting clinicians in early detection.

## Dataset

The project used the [OASIS-1 dataset](https://www.oasis-brains.org), containing brain MRI scans from subjects with varying degrees of cognitive impairment. The dataset was preprocessed to focus on image slices and prevent data leakage.

### Categories:
- **Non-Demented**: 67,222 images
- **Very Mild Dementia**: 13,725 images
- **Mild Dementia**: 5,002 images
- **Moderate Dementia**: 488 images

## Data Preprocessing

Key challenges included **subject-based organization** to prevent data leakage and **class balancing** to handle the large discrepancy in image counts across categories.

## Binary Classification

The classification was framed as a binary task: detecting the presence of dementia (combining all dementia categories into one) vs. non-demented subjects.

## Our Models

### 1. Logistic Regression

As a baseline, logistic regression achieved 67.4% accuracy.

### 2. Convolutional Neural Network (CNN)

Our custom CNN achieved **83% validation accuracy**, outperforming logistic regression by a significant margin.

### 3. Transfer Learning with MobileNetV2

A pre-trained model, MobileNetV2, was tested but performed worse than the CNN, reaching 72% accuracy.

## Discussion

Confusion matrices revealed both models had issues with false negatives (missing dementia cases) and false positives (incorrectly labeling non-demented subjects as having dementia).

## Limitations

- **Limited Dataset Diversity**: The model might not generalize well to other populations.
- **Binary Classification Simplification**: Loss of ability to measure disease severity.
- **Technical Limitations**: Limited computational power prevented more complex models.

## Conclusion

Convolutional Neural Networks effectively detect dementia in brain MRI scans, achieving an 83% validation accuracy. However, the model’s false negatives highlight areas for improvement.

Future work will extend the model to multi-class classification and incorporate more diverse datasets.

---

## Links to Code Blocks for Figures

1. **Figure 1 - MRI Scan Samples**
2. **Figure 2 - CNN Confusion Matrix**
3. **Figure 3 - Transfer Learning Confusion Matrix**
---


## Citations

1. Alzheimer’s Association. What is Alzheimer’s? Available: [link](https://www.alz.org/alzheimers-dementia/what-is-alzheimers)
2. National Institute on Aging. What Happens to the Brain in Alzheimer’s Disease? Available: [link](https://www.nia.nih.gov/health/alzheimers-causes-and-risk-factors/what-happens-brain-alzheimers-disease)
3. OASIS-1: Cross-Sectional Data. Available: [link](https://www.oasis-brains.org)
