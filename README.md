

# 📊 Task 3 – Decision Tree Classifier (Bank Marketing Dataset)

## 📌 Objective

Build a **Decision Tree Classifier** to predict whether a customer will subscribe to a term deposit based on demographic and behavioral data.

Dataset Used: **Bank Marketing Dataset**
Source: UCI Machine Learning Repository

---

## 📂 Dataset Overview

* Total Rows: **4,521**
* Total Columns: **17**
* Target Variable: `y` (Subscription Status)

### Numerical Features:

* age
* balance
* day
* duration
* campaign
* pdays
* previous

### Categorical Features:

* job
* marital
* education
* default
* housing
* loan
* contact
* month
* poutcome

---

## 🧹 Data Cleaning

* No missing values found
* No duplicate rows detected
* Retained `"unknown"` categories in job, education, and contact
* Removed weak / data-leakage features:

  * `day`
  * `duration`

---

## 📊 Exploratory Data Analysis (EDA)

* 88% customers did not subscribe
* 12% customers subscribed (Imbalanced dataset)
* Most customers aged between 30–50
* Customers without housing or personal loans were more likely to subscribe
* Higher balance customers showed slightly better subscription probability
* Blue-collar, management, and technician were dominant job categories

---

## ⚙️ Data Preprocessing

* Converted target variable:

  * yes → 1
  * no → 0
* Converted binary categorical features to numeric
* Applied One-Hot Encoding for multi-class categorical variables
* Split dataset into training and testing sets

---

## 🌳 Model Training

Model Used: **Decision Tree Classifier**

Initial model showed high accuracy but poor performance on minority class (subscribers).

To improve:

* Applied `class_weight='balanced'`
* Tuned:

  * max_depth
  * min_samples_split
  * min_samples_leaf

---

## 📈 Final Model Performance

| Metric              | Value |
| ------------------- | ----- |
| Accuracy            | 82%   |
| Precision (Class 1) | 0.30  |
| Recall (Class 1)    | 0.38  |
| F1-Score (Class 1)  | 0.33  |

### 📌 Key Insight:

Although overall accuracy decreased slightly after tuning, recall for actual subscribers improved significantly.

This demonstrates the importance of optimizing for minority class detection in imbalanced classification problems.

---

## 🎯 Conclusion

* Accuracy alone is not sufficient for imbalanced datasets.
* Class balancing significantly improves detection of potential subscribers.
* Decision Trees provide interpretable results but may be limited in highly imbalanced problems.
* Further improvement could be achieved using ensemble methods like Random Forest or Gradient Boosting.

---


