# Breast Cancer Diagnosis Using Thermal Images

## Overview
This project applies **deep learning and genetic algorithms** to diagnose breast cancer using thermal images. The approach involves **image preprocessing, feature extraction using ResNet-50, feature selection via Genetic Algorithm (GA), and classification using Random Forest**.

## Objective
The goal is to develop an **efficient and accurate** breast cancer detection model using **thermal imaging** and **feature selection optimization**.

## Dataset
- **Source:** [Kaggle - Thermal Images for Breast Cancer Diagnosis](https://www.kaggle.com/datasets/asdeepak/thermal-images-for-breast-cancer-diagnosis-dmrir)
- **Description:** Thermal images labeled as `"Positive"` (cancer) and `"Negative"` (healthy)
- **Data Split:**
  - **Training Data:** Cancer-positive and healthy samples
  - **Testing Data:** Separate set for validation

## Methodology
### 1. Data Preprocessing
- Loaded images and assigned binary labels **(1 = Positive, 0 = Negative)**
- Converted images to **grayscale (1 channel)**
- Resized to **224x224 pixels** (for ResNet-50 compatibility)
- Normalized pixel values for uniform distribution

### 2. Custom Dataset Class (PyTorch)
- Created a **CustomDataset** class to handle loading and transformations
- Automates **resizing and normalization**
- Simplifies data handling in PyTorch's **DataLoader**

### 3. Feature Extraction with ResNet-50
- Used **ResNet-50 (pretrained on ImageNet)** to extract high-level features
- Adjusted input layer for grayscale images (1 channel)
- Converted images into **feature vectors** for classification

### 4. Feature Selection Using Genetic Algorithm
- **Genetic Algorithm (GA)** applied to select the most relevant features
- **Fitness Metric:** Accuracy
- **GA Setup:**
  - **Population Size:** 25 individuals (feature subsets)
  - **Generations:** 8
  - **Selection Strategy:** Optimizes feature subsets for better classification

### 5. Classification with Random Forest
- Used **Random Forest Classifier** for final classification
- Evaluated performance using multiple metrics

## Performance Metrics
| Metric  | Test Set | Cross-Validation |
|---------|---------|-----------------|
| Accuracy | `64.56%` | `79.18%` |
| Precision | `68.12%` | `79.43%` |
| Recall | `64-0%` | `78.75%` |
| F1 Score | `64.77%` | `79.01%` |

## Installation & Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/breast-cancer-thermal.git
   cd breast-cancer-thermal
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
3. Download and prepare the dataset as per instructions.
4. Run the training script:
   ```bash
   python train.py

## Contributors
- Dharavath Shreyas
- Swarna Praneeth Chandra
- Prachi
