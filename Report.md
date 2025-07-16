# Diabetes Prediction using Machine Learning

## **California State University, Long Beach** 

## **Computer Engineering and Computer Science Department** 

**Created by**:  
Kelly Pham & Khoa Vu

---

## Abstract

Diabetes remains one of the leading global health concerns, emphasizing the need for early identification of at-risk individuals. This study explores the application of ensemble machine learning models to predict the presence of diabetes based on demographic and clinical attributes.

We utilized a dataset containing features such as:
- Age
- Gender
- Body Mass Index (BMI)
- Blood Glucose Level
- HbA1c Level
- Hypertension
- Heart Disease
- Smoking History

The Random Forest ensemble method was applied, along with SMOTE to handle class imbalance. Evaluation metrics included precision, recall, accuracy, F1-score, confusion matrix, and ROC AUC. The SMOTE-enhanced model outperformed others, especially in identifying diabetic patients.

---

## Introduction

Early detection of diabetes is critical for medical intervention. This project employs Random Forest for binary classification (diabetic vs. non-diabetic).

We tested three model configurations:
1. **Full Model**: Using all features
2. **Limited Model**: Using only HbA1c and blood glucose
3. **SMOTE Model**: Full model with SMOTE class balancing

### Evaluation Metrics:
- **Confusion Matrix**
- **Precision**
- **Recall**
- **F1-Score**
- **Accuracy**
- **ROC Curve and AUC**

---

## Problem Statement

We aim to classify individuals as either diabetic (`1`) or non-diabetic (`0`) based on eight risk-related features. The dataset is imbalanced, with more non-diabetic samples, so we apply SMOTE to improve sensitivity for minority (diabetic) class.

---

## Model Improvement Techniques

1. **Baseline (Full Feature Set)**
   - Accuracy: 97%
   - AUC: 0.95

2. **Limited Model (Top 2 Features: HbA1c, Glucose)**
   - Accuracy: 97%
   - Slight drop in recall

3. **SMOTE Model (Balanced Classes)**
   - Accuracy: 96%
   - AUC: 0.96
   - Higher recall for diabetic class

---

## Experimental Results

### 1. Full Model

**Confusion Matrix:**

[[18221 62]

[ 543 1174]]


**Classification Report:**
- Precision (0): 0.97
- Recall (0): 1.00
- Precision (1): 0.95
- Recall (1): 0.68
- Accuracy: 0.97

---

### 2. Limited Model (HbA1c & Glucose)

**Confusion Matrix:**

[[18283 0]

[ 576 1141]]


**Classification Report:**
- Precision (1): 1.00
- Recall (1): 0.66
- Accuracy: 0.97

---

### 3. SMOTE Model (Balanced)

**Confusion Matrix:**

[[17965 335]

[ 447 1253]]


**Classification Report:**
- Precision (1): 0.79
- Recall (1): 0.74
- Accuracy: 0.96

---

## ROC Curve & AUC Comparison

| Model          | AUC Score |
|----------------|-----------|
| SMOTE Model    | 0.96      |
| Full Model     | 0.95      |
| Limited Model  | 0.94      |

> ROC curves showed SMOTE had the best ability to distinguish between diabetic and non-diabetic cases.

---

## Analysis & Discussion

- **Precision vs. Recall**: Prioritized recall to minimize false negatives in medical diagnosis.
- **Trade-Offs**:
  - Full Model: Highest accuracy, lower recall.
  - Limited Model: High precision, low recall.
  - SMOTE Model: Balanced precision/recall, best AUC.
- **Why SMOTE Works**: Improved recall by generating synthetic minority samples. Acceptable trade-off in precision.

### Sources of Error:
- SMOTE may introduce noise.
- Limited model omits relevant features.
- Full model may risk overfitting.

---

## Recommendations for Future Work

- Optimize classification thresholds.
- Engineer new features (e.g., interaction terms).
- Apply cross-validation and test on external datasets.

---

## Conclusion

Among the models tested, the **SMOTE-enhanced Random Forest model** proved most effective for diabetes detection. It offered the best recall and AUC, which are crucial in clinical diagnostics. Improving early identification of diabetic patients can lead to better health outcomes and reduced risk of complications.

---
