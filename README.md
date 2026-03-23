# 💳 Credit Card Fraud Detection with Machine Learning

## 📌 Overview
This project presents an end-to-end machine learning pipeline for detecting fraudulent credit card transactions. It combines **geospatial analysis**, **feature engineering**, **class imbalance handling**, and **model optimization** to achieve high-performance fraud detection.

The project demonstrates how domain-driven feature engineering and advanced models like **XGBoost** significantly improve detection performance.

---

## 🚀 Key Features
- 📍 Geospatial analysis using transaction & merchant locations
- 🧠 Advanced feature engineering (distance, temporal, behavioral)
- ⚖️ Handling class imbalance using **SMOTE**
- 🤖 Model comparison:
  - Logistic Regression
  - Random Forest
  - XGBoost
- 🔍 Hyperparameter tuning using GridSearchCV
- 📊 Custom evaluation with Recall, Precision, F1, ROC-AUC
- 📈 Feature importance using permutation importance

---

## 📂 Dataset
The dataset contains transaction-level information including:
- Transaction amount
- Customer demographics
- Merchant details
- Geographic coordinates (lat/long)
- Timestamp
- Fraud label (`is_fraud`)

---

## 🔍 Exploratory Data Analysis (EDA)

### 🌍 Geospatial Visualization
- Customer transaction locations
- Merchant locations
- Heatmaps for transaction density

### ⏱ Temporal Analysis
- Extracted:
  - Transaction hour
  - Day of the week

---

## 🛠 Feature Engineering

### 📌 Key Features Created:
- **Distance between customer & merchant** (Haversine formula)
- **Distance-to-amount ratio**
- **User age** (derived from DOB)
- **Transaction hour & weekday**

These features help capture **fraud patterns**, such as:
- Unusual transaction distances
- Time-based anomalies
- Behavioral inconsistencies

---

## ⚙️ Data Preprocessing
- One-hot encoding for categorical features
- Standard scaling for numerical features
- ColumnTransformer + Pipeline
- Stratified train-test split

---

## ⚖️ Handling Class Imbalance
Fraud datasets are highly imbalanced. To address this:

- Applied **SMOTE (Synthetic Minority Oversampling Technique)** on training data only
- Preserved realistic evaluation on test data

---

## 🤖 Models & Optimization

### Models Used:
- Logistic Regression (baseline)
- Random Forest
- XGBoost (best performing)

### Hyperparameter Tuning:
- GridSearchCV (5-fold CV)
- Optimized for **Recall** (critical for fraud detection)

---

## 📊 Evaluation Metrics

Custom evaluation function includes:
- Recall (priority for fraud detection)
- Precision
- F1 Score
- ROC-AUC

---

## 🏆 Results

| Model               | Recall | Precision | F1 Score | ROC-AUC |
|--------------------|--------|----------|---------|---------|
| Logistic Regression| 0.82   | 0.49     | 0.61    | —       |
| Random Forest      | 0.84   | 0.92     | 0.88    | —       |
| XGBoost ✅         | 0.93   | 0.93     | 0.93    | 0.996   |

### ✅ Key Insight:
**XGBoost achieved the best performance**, providing a strong balance between detecting fraud and minimizing false positives.

---

## 📈 Feature Importance
- Used permutation importance
- Identified top predictive features:
  - Distance-related features
  - Transaction amount
  - Time-based features

---

## 🧠 Key Takeaways
- Feature engineering is critical in fraud detection
- Geospatial features significantly improve model performance
- SMOTE effectively handles class imbalance
- XGBoost outperforms traditional models in structured data problems

---

## 🛠 Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- Folium (Geospatial visualization)
- Matplotlib
