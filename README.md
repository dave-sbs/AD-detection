# Classifying Dementia in Brain MRI Scans with Convolutional Neural Networks

This project leverages Convolutional Neural Networks (CNNs) to detect signs of dementia in brain MRI scans. The goal is to provide an early detection tool that can assist clinicians in identifying dementia in its early stages, aiding in timely interventions.

## Table of Contents

1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Data Preprocessing](#data-preprocessing)
4. [Binary Classification](#binary-classification)
5. [Our Models](#our-models)
6. [Discussion](#discussion)
7. [Reproduce the Models and Figure](#reproduce-the-models-and-figures)
8. [Limitations](#limitations)
9. [Conclusion](#conclusion)

---

## Introduction

Alzheimer's disease, a leading cause of dementia, affects millions of people globally. The project's aim is to develop a model that can classify brain MRI scans into "Dementia" or "Non-Demented" categories using a CNN, assisting clinicians in early detection. 

## Dataset

The project used the [OASIS-1 dataset](https://www.oasis-brains.org), containing brain MRI scans from subjects with varying degrees of cognitive impairment. The dataset was preprocessed to focus on image slices and prevent data leakage. The actual image folders used to train our model can be downloaded from this link: https://www.kaggle.com/datasets/ninadaithal/imagesoasis. As there are too many image files to upload them all to GitHub, you will have to download them to your own computer directly from Kaggle. 

### Categories:
- **Non-Demented**: 67,222 images
- **Very Mild Dementia**: 13,725 images
- **Mild Dementia**: 5,002 images
- **Moderate Dementia**: 488 images

## Data Preprocessing

Key challenges included subject-based organization to prevent data leakage and class balancing to handle the large discrepancy in image counts across categories.

## Binary Classification

The classification was framed as a binary task: detecting the presence of dementia (combining all dementia categories into one) vs. non-demented subjects.

## Our Models

### 1. Logistic Regression

As a baseline, logistic regression achieved 67.4% accuracy.

### 2. Convolutional Neural Network (CNN)

Our custom CNN achieved 83% validation accuracy, outperforming logistic regression by a significant margin.

### 3. Transfer Learning with MobileNetV2

A pre-trained model, MobileNetV2, was tested but performed worse than the CNN, reaching 72% accuracy.

## Discussion

Confusion matrices revealed both models had issues with false negatives (missing dementia cases) and false positives (incorrectly labeling non-demented subjects as having dementia).

## Reproduce the Models and Figures

To run this project on your own machine, follow these steps:

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/dementia-mri-classification.git
cd dementia-mri-classification
```

### 2. Download the Dataset

This project uses a preprocessed version of the OASIS-1 brain MRI dataset. The folders were too large to upload to GitHub, so you can download it here from Kaggle: https://www.kaggle.com/datasets/ninadaithal/imagesoasis

Once the ZIP file is extracted, move this folder into the root of this project and rename it to: 
```
./OASIS Data/
```

Your folder structure should look like this:

```
OASIS Data/
├── Mild Dementia/
├── Moderate Dementia/
├── Non Demented/
└── Very mild Dementia/
```

### 3. Install Dependencies and Run the Code

Finally, install the required dependencies and run the "oasis_data_classification_model.ipynb" jupyter notebook file cells in order.


## Limitations

- **Limited Dataset Diversity**: The model might not generalize well to other populations.
- **Binary Classification Simplification**: Loss of ability to measure disease severity.
- **Technical Limitations**: Limited computational power prevented more complex models.

## Conclusion

Convolutional Neural Networks effectively detect dementia in brain MRI scans, achieving an 83% validation accuracy. However, the model’s false negatives highlight areas for improvement.

Future work will extend the model to multi-class classification and incorporate more diverse datasets.

---

## Links to Code Blocks for Figures

The figures mentioned below are located in the 'blog_figures' folder.

1. **Figure 1 - MRI Scan Samples** (https://github.com/dave-sbs/AD-detection/blob/main/oasis_data_classification_model.ipynb#display-example-mri-scans-from-each-class)
2. **Figure 2 - CNN Confusion Matrix** (https://github.com/dave-sbs/AD-detection/blob/main/oasis_data_classification_model.ipynb#create-confusion-matrices)
3. **Figure 3 - Transfer Learning Confusion Matrix** (https://github.com/dave-sbs/AD-detection/blob/main/oasis_data_classification_model.ipynb#create-confusion-matrices)
---

