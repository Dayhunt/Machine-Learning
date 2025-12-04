# Data Preprocessing — 

## **1. What is Data Preprocessing?**

Data preprocessing means **cleaning and transforming raw data** so that machine learning models can understand and learn from it.  
I like to think of it as **preparing ingredients before cooking** — the model performs well only when the data is clean.

### **Key Goals:**
- Handle missing values  
- Remove noise and outliers  
- Make data consistent  
- Transform data into a suitable format  

---

## **2. Why Is It Important?**

- Most ML models assume **numerical, clean, and complete** data.  
- Proper preprocessing improves **accuracy, training speed, and model stability**.

---

## **3. Common Steps in Data Preprocessing**

---

### **Step 1: Handling Missing Data**

Missing values can weaken model performance, so we either fill them or remove them.

#### **Methods:**
- **Remove rows/columns**  
  - Use when missing values are very few and do not affect data meaning.

- **Imputation (filling missing values):**  
  - **Mean / Median / Mode** → numerical data  
  - **Most Frequent** → categorical data  
  - **KNN Imputer** → advanced method using nearest neighbors  

**When to use:**  
- Mean → symmetric distributions  
- Median → skewed data  
- Mode → categorical data  

---

### **Step 2: Handling Categorical Data**

Machine learning models don’t understand text, so encoding is necessary.

#### **Methods:**
- **Label Encoding**  
  - Converts categories to numbers (0, 1, 2…).  
  - Best for **ordinal data** (Low < Medium < High).

- **One-Hot Encoding**  
  - Creates binary columns for each category.  
  - Best for **nominal data** (no order), like colors.

- **Target/Frequency Encoding**  
  - Useful for **high-cardinality columns**.

---

### **Step 3: Feature Scaling**

Some algorithms are sensitive to the scale of data (SVM, KNN, Logistic Regression, Neural Networks).

#### **Common Scaling Techniques:**
- **Normalization (Min-Max Scaling)**  
  - Converts values to range **0–1**  
  - Used in **Neural Networks**

- **Standardization (Z-Score)**  
  - Mean = 0, Standard deviation = 1  
  - Used in **SVM and PCA**

- **Robust Scaling**  
  - Uses median and IQR  
  - Useful when **outliers** are present

---

### **Step 4: Handling Outliers**

Outliers can heavily influence the model.

#### **Methods:**
- **IQR Method**  
  - Remove points outside **Q1 − 1.5×IQR** and **Q3 + 1.5×IQR**

- **Z-Score Method**  
  - Remove points where **Z > 3**

- **Capping/Flooring**  
  - Set max and min thresholds

---

### **Step 5: Feature Engineering / Transformation**

Sometimes raw features need transformation to help the model learn better.

#### **Common Techniques:**
- **Log / Square Root Transform** → reduces skewness  
- **Polynomial Features** → captures non-linear relationships  
- **Binning** → converts continuous to categorical  
- **Interaction Features** → multiplication or combination of features  

---

### **Step 6: Feature Selection / Dimensionality Reduction**

Too many features create noise and cause overfitting.

#### **Methods:**

**Filter Methods:**  
- Correlation  
- Chi-square Test  

**Wrapper Methods:**  
- Recursive Feature Elimination (RFE)

**Embedded Methods:**  
- Lasso Regression  
- Tree-based Feature Importance  

**Dimensionality Reduction:**  
- **PCA**  
- **t-SNE** (used for visualization)
  
---

### **Step 7: Splitting Data**

#### **Common Approaches:**
- **Train-Test Split** → typically 70:30 or 80:20  
- **Cross-Validation (K-Fold)** → improves reliability  
- **Avoiding Data Leakage** → extremely important in interviews  

---
