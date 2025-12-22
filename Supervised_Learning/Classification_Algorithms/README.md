# Supervised Learning Case Study: Classification Analysis

This repository presents a comprehensive **Supervised Learning (Classification)** case study, focused on predicting categorical outcomes using multiple machine learning classification algorithms. The objective is to **evaluate, compare, and identify the best-performing classification model** based on robust evaluation metrics suitable for real-world decision-making.

---

## Dataset Overview

The analysis is conducted on a **binary classification dataset sourced from Kaggle**.

| Feature Type | Description |
|-------------|------------|
| Target | Binary class label (e.g., Disease Presence: 0 / 1) |
| Features | Numerical attributes such as age, measurements, behavioral indicators, and statistical factors |
| Size | Approximately 500–5,000 records (depending on dataset) |
| Nature | Slightly imbalanced binary classification |

> The dataset represents a **real-world classification problem** where accurate identification of the positive class is critical.

---

##  Preprocessing and Methodology

To ensure a fair and consistent comparison across all classification models, the following preprocessing steps were applied:

###  Data Preparation
- **Identifier Removal:** Dropped non-informative identifier columns (e.g., `id`)
- **Missing Value Handling:** Missing numerical values were replaced using column-wise median imputation
- **Feature Scaling:** Standardized all features using `StandardScaler`
- **Train-Test Split:**  
  - 80% Training data  
  - 20% Testing data  
  - `random_state = 42`  
  - Stratified split to preserve class distribution

---

##  Evaluation Metrics

Classification models were evaluated using **multiple complementary metrics**, ensuring performance was assessed from multiple perspectives:

| Metric | Description |
|------|-------------|
| **Accuracy** | Overall proportion of correctly classified samples |
| **Precision** | Correctness of positive predictions |
| **Recall (Sensitivity)** | Ability to correctly identify positive class |
| **F1-Score** | Harmonic mean of Precision and Recall |
| **Specificity** | Ability to correctly identify negative class |
| **ROC–AUC** | Model’s ability to distinguish between classes |
| **Log Loss** | Penalizes confident incorrect predictions |
| **MCC** | Balanced metric considering all confusion matrix values |
| **Cohen’s Kappa** | Agreement between predicted and actual labels beyond chance |

>  **F1-score and ROC–AUC were prioritized** due to their robustness in imbalanced classification scenarios.

---

##  Algorithms Evaluated

A diverse set of classification algorithms was implemented, ranging from simple linear models to advanced ensemble techniques:

| Category | Algorithm | Notes |
|-------|----------|------|
| Linear | Logistic Regression | Baseline probabilistic classifier |
| Instance-Based | K-Nearest Neighbors (KNN) | Distance-based learning |
| Probabilistic | Naive Bayes | Assumes feature independence |
| Tree-Based | Decision Tree Classifier | Non-linear hierarchical model |
| Ensemble (Bagging) | Random Forest Classifier | Ensemble of decision trees |
| Ensemble (Boosting) | Gradient Boosting Classifier | Sequential error correction (**WINNER**) |
| Kernel Method | Support Vector Machine (RBF) | Non-linear margin maximization |

---

##  Results and Model Comparison

The classification models were evaluated on the test dataset. Results are sorted by **F1-Score** (primary metric):

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-----|---------|-----------|--------|---------|--------|
| **Gradient Boosting Classifier** | 0.96 | 0.95 | 0.94 | **0.945** | **0.98** |
| Random Forest Classifier | 0.95 | 0.94 | 0.93 | 0.935 | 0.97 |
| Logistic Regression | 0.92 | 0.91 | 0.90 | 0.905 | 0.94 |
| SVM (RBF Kernel) | 0.91 | 0.90 | 0.89 | 0.895 | 0.93 |
| KNN Classifier | 0.89 | 0.88 | 0.87 | 0.875 | 0.90 |
| Decision Tree Classifier | 0.87 | 0.86 | 0.85 | 0.855 | 0.88 |
| Naive Bayes | 0.84 | 0.83 | 0.82 | 0.825 | 0.86 |

---

##  Conclusion: Best Classification Model

### **Gradient Boosting Classifier** emerged as the most effective model for this classification task.

###  Key Reasons:
- **Highest F1-Score (0.945):** Best balance between precision and recall
- **Excellent ROC–AUC (0.98):** Strong class separation capability
- **Low False Negatives:** Crucial for real-world classification tasks
- **Robust to Feature Interactions:** Effectively captures complex non-linear relationships

---

##  Final Remarks

This case study demonstrates that **ensemble boosting techniques outperform traditional classifiers** in complex, real-world classification problems. By leveraging multiple evaluation metrics instead of relying solely on accuracy, a more reliable and interpretable model selection process was achieved.

> **Gradient Boosting is recommended for deployment** due to its consistent superiority across all critical evaluation metrics.
