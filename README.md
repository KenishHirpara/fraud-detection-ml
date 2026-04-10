# 💳 Advanced Credit Card Fraud Detection

## 📌 Overview

This project presents a **cost-sensitive machine learning framework** for detecting fraudulent credit card transactions in highly imbalanced datasets.

Unlike traditional approaches that optimize accuracy, this work reframes fraud detection as an **Expected Risk Minimization problem**, where predictions are aligned with **real-world financial impact**.

---

## 🚀 Key Features

* 🔹 Controlled SMOTE (0.2 ratio) to handle extreme class imbalance
* 🔹 Domain-driven Feature Engineering (Temporal + Log Scaling)
* 🔹 Cost-Sensitive Learning with asymmetric penalties
* 🔹 Ensemble Models: XGBoost, Random Forest, LightGBM
* 🔹 Evaluation using PR-AUC, ROC-AUC, F1-Score, and Financial Cost

---

## 📊 Dataset

The dataset used in this project is publicly available on Kaggle:

👉 https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

### 📌 Dataset Details

* Total Transactions: **284,807**
* Fraud Cases: **492 (~0.17%)**
* Features: **V1–V28 (PCA transformed) + Time + Amount**

⚠️ Due to size constraints, the dataset is **not included** in this repository.

---

## 🧠 Methodology

### 1. Feature Engineering

* Extracted **temporal features** (Hour, Is_Night)
* Applied **log transformation** on transaction amount
* Created **relational features** between PCA components

---

### 2. Handling Class Imbalance

* Used **Controlled SMOTE (ratio = 0.2)**
* Prevents overfitting caused by full oversampling

---

### 3. Models Used

* Random Forest
* XGBoost (Best Performing)
* LightGBM
* Support Vector Machine (SVM)
* Isolation Forest (Baseline)

---

### 4. Cost-Sensitive Evaluation

Instead of accuracy, we minimize financial loss:

[
Cost = (FN \times 500) + (FP \times 10)
]

* False Negative → High loss (missed fraud)
* False Positive → Low loss (customer inconvenience)

---

## 📈 Results

| Model            | Precision | Recall    | F1 Score  | Cost ($) |
| ---------------- | --------- | --------- | --------- | -------- |
| Random Forest    | 1.000     | 0.714     | 0.833     | 1000     |
| **XGBoost**      | **0.857** | **0.857** | **0.857** | **510**  |
| LightGBM         | 0.714     | 0.714     | 0.714     | 1020     |
| SVM              | 0.833     | 0.714     | 0.769     | 1010     |
| Isolation Forest | 0.043     | 0.142     | 0.066     | 3220     |

### 🏆 Best Model: XGBoost

* Achieves optimal balance between Precision and Recall
* Reduces financial cost by **~49% compared to Random Forest**

---

## 📉 Visualizations

* ROC Curve
* Precision-Recall Curve
* Confusion Matrix
* Feature Importance Plot

---

## ⚙️ Technologies Used

* Python
* Scikit-learn
* XGBoost
* LightGBM
* Pandas, NumPy
* Matplotlib, Seaborn

---

## 📁 Project Structure

```
fraud-detection-ml/
│
├── Research.ipynb
├── Research.py
├── README.md
├── roc_curve.png
├── pr_curve.png
├── requirements.txt
```

---

## 🔬 Key Insight

> Fraud detection should not be treated as a classification problem, but as an **asymmetric risk minimization problem**.

---

## ⚠️ Limitations

* Dataset is anonymized (PCA), limiting interpretability
* SMOTE generates synthetic samples
* Model does not handle real-time concept drift

---

## 🔮 Future Work

* Deep Learning (LSTM, Transformers)
* Real-time fraud detection systems
* Concept drift adaptation
* Fairness and bias analysis

---

## 👨‍💻 Author

**Kenish Hirpara**
B.Tech Computer Science and Engineering
Karnavati University

---

## ⭐ If you like this project

Give it a ⭐ on GitHub!

---
