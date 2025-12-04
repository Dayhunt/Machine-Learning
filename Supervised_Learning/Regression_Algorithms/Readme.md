# Supervised Learning Case Study: House Price Prediction

This repository contains a comprehensive case study on **Supervised Learning (Regression)**, focusing on predicting house prices using a diverse set of machine learning algorithms. The goal is to evaluate, compare, and identify the best-performing model based on key regression metrics.

---

## Dataset Overview

The analysis is performed on the **`House_Price_India.csv`** dataset.

| Feature Type | Description |
| :--- | :--- |
| **Target** | `Price` (The final predicted value) |
| **Features** | `number of bedrooms`, `living area`, `Built Year`, `Lattitude`, `Longitude`, `Distance from the airport`, etc. |
| **Size** | Approximately 14,600 house records. |

---

##  Preprocessing and Methodology

The following standard steps were applied to ensure fair comparison across all models:

1.  **Data Cleaning:** Dropped identifier columns (`id`).
2.  **Missing Value Handling:** Handled any potential missing values by filling them with the **median** of the respective column.
3.  **Feature Scaling:** All features were scaled using **StandardScaler** to normalize the data, which is crucial for models like Linear Regression and SVR.
4.  **Train-Test Split:** The dataset was split into an **80% training set** and a **20% testing set** (`random_state=42`).
5.  **Evaluation Metrics:** Models were assessed using:
    * **R-squared ($R^2$):** Measures the proportion of the variance in the dependent variable that is predictable from the independent variables. (Higher is better)
    * **Root Mean Squared Error (RMSE):** Measures the average magnitude of the errors. (Lower is better)
    * **Mean Absolute Error (MAE):** Measures the average absolute difference between predicted and actual values. (Lower is better)

---

##  Algorithms Tested

A wide range of regression algorithms, from simple linear models to complex ensemble methods, were implemented and compared:

| Category | Algorithm | Notes |
| :--- | :--- | :--- |
| **Linear** | **Multiple Linear Regression** | Standard baseline model. |
| **Polynomial** | **Polynomial Regression (Degree 2)** | Linear Regression applied to 2nd-degree polynomial features. |
| **Regularized** | **Ridge Regression (L2)** | Linear model with L2 regularization to prevent overfitting. |
| **Regularized** | **Lasso Regression (L1)** | Linear model with L1 regularization for feature selection. |
| **Regularized** | **Elastic Net (L1 + L2)** | Combines L1 and L2 penalties. |
| **Instance-Based** | **KNN Regression** | Predicts based on the values of the nearest neighbors. |
| **Tree-Based** | **Decision Tree Regressor** | Non-linear model with a single decision tree. |
| **Ensemble** | **Random Forest Regressor** | Ensemble of decision trees (Bagging). |
| **Ensemble** | **Gradient Boosting Regressor** | Ensemble of weak prediction models (Boosting). **(WINNER)** |
| **Kernel Method** | **SVR (RBF Kernel)** | Non-linear Support Vector Machine for regression. |
| **Boosting** | **XGBoost Regressor** | *(Skipped due to environmental library constraints.)* |

---

##  Results and Comparison

The performance metrics for all models on the test set are summarized below, sorted by the **$R^2$ Score**:

| Model | R² | RMSE | MAE |
|:--------------------------------|--------:|------------:|-------------:|
| **Gradient Boosting Regressor** | **0.8918** | **126,556.8615** | **74,606.1927** |
| Random Forest Regressor | 0.8810 | 132,699.0394 | 70,132.9743 |
| Polynomial Regression (Degree 2) | 0.8183 | 163,968.7996 | 101,389.3448 |
| Decision Tree Regressor | 0.7912 | 175,783.9004 | 91,431.9282 |
| KNN Regression | 0.7656 | 186,241.2581 | 99,477.1502 |
| Multiple Linear Regression | 0.7020 | 210,018.9071 | 125,366.1794 |
| Lasso Regression (L1) | 0.7020 | 210,018.9068 | 125,366.1793 |
| Ridge Regression (L2) | 0.7020 | 210,019.7542 | 125,362.5326 |
| Elastic Net (L1 + L2) | 0.7020 | 210,019.9810 | 125,354.0690 |
| SVR (RBF Kernel) | 0.0598 | 373,012.8845 | 200,019.0670 |

---

## Conclusion: Best Model

The **Gradient Boosting Regressor** is the superior model for this house price prediction task.

* **$R^2$ Score of 0.8918:** This indicates the model successfully explains over **89%** of the variance in house prices, demonstrating excellent predictive power.
* **Lowest RMSE:** With an RMSE of approximately **\$126,557**, the average prediction error is the lowest among all tested algorithms.

This highlights the effectiveness of **ensemble boosting techniques** in capturing the complex, non-linear feature interactions often present in real-estate datasets.
