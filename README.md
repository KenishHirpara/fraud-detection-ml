# 💳 Advanced Credit Card Fraud Detection

### 🚀 Cost-Sensitive Machine Learning Framework for Real-World Fraud Detection

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/ML-XGBoost-orange)
![Status](https://img.shields.io/badge/Project-Research%20Level-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Overview

This project presents a **research-driven machine learning framework** for detecting fraudulent credit card transactions in highly imbalanced datasets.

Unlike traditional approaches that optimize accuracy, this work reframes fraud detection as an **Expected Risk Minimization problem**, where predictions are aligned with **real-world financial loss rather than statistical correctness**.

---

## 🚀 Key Highlights

* Controlled SMOTE (0.2 ratio) to avoid overfitting
* Domain-driven Feature Engineering (Temporal + Log Scaling)
* Cost-Sensitive Learning with asymmetric penalties
* Ensemble Models: XGBoost, Random Forest, LightGBM
* Evaluation using PR-AUC, ROC-AUC, F1-Score, and Financial Cost

---

## 📊 Dataset

The dataset used in this project is publicly available on Kaggle:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

### 📌 Dataset Details

* Total Transactions: **284,807**
* Fraud Cases: **492 (~0.17%)**
* Features: **V1–V28 (PCA transformed), Time, Amount**

⚠️ Due to size constraints, the dataset is not included in this repository.

---

## 🧠 Methodology

### 1. Feature Engineering

* Temporal extraction (Hour, Is_Night)
* Log transformation of transaction amount
* Relational feature creation

---

### 2. Handling Class Imbalance

* Controlled SMOTE with sampling ratio 0.2
* Prevents synthetic overfitting and boundary distortion

---

### 3. Models Evaluated

* XGBoost (Best Performing Model)
* Random Forest
* LightGBM
* Support Vector Machine
* Isolation Forest (Baseline)

---

### 4. Cost-Sensitive Evaluation

Financial cost function:

Cost = (FN × 500) + (FP × 10)

* False Negative → Severe financial loss
* False Positive → Minor inconvenience

---

## ⚡ Performance Summary

* Best Model: XGBoost
* F1 Score: 0.857
* PR-AUC: 0.899
* Cost Reduction: ~49%

Optimized for **financial risk**, not just accuracy.

---

## 📈 Results

| Model            | Precision | Recall    | F1 Score  | Cost ($) |
| ---------------- | --------- | --------- | --------- | -------- |
| Random Forest    | 1.000     | 0.714     | 0.833     | 1000     |
| **XGBoost**      | **0.857** | **0.857** | **0.857** | **510**  |
| LightGBM         | 0.714     | 0.714     | 0.714     | 1020     |
| SVM              | 0.833     | 0.714     | 0.769     | 1010     |
| Isolation Forest | 0.043     | 0.142     | 0.066     | 3220     |

---

## 📉 Visualizations

### ROC Curve

![ROC Curve](roc_curve.png)

### Precision-Recall Curve

![PR Curve](pr_curve.png)

---

## ▶️ How to Run

1. Clone the repository:
   git clone https://github.com/KenishHirpara/fraud-detection-ml.git

2. Navigate into project folder:
   cd fraud-detection-ml

3. Install dependencies:
   pip install -r requirements.txt

4. Run the model:
   python model.py

⚠️ Replace sample dataset with full dataset for real results.

---

## 🔁 Reproducibility

This project is fully reproducible:

* Download dataset from Kaggle
* Place it in project directory
* Run provided scripts or notebook

All preprocessing, training, and evaluation steps are included.

---

## 🧪 Experimental Setup

* Train/Test Split: 80/20 (Stratified)
* SMOTE Ratio: 0.2
* Evaluation Metrics: F1, PR-AUC, ROC-AUC
* Cost Function: FN = 500, FP = 10

---

## 🌍 Real-World Relevance

* Designed for financial fraud detection systems
* Handles extreme class imbalance
* Optimized for minimizing financial loss
* Suitable for real-time deployment pipelines

---

## 🧠 Research Insight

Fraud detection should not be treated as a classification problem, but as an **asymmetric risk minimization problem**.

---

## ⚠️ Limitations

* PCA features reduce interpretability
* Synthetic data from SMOTE
* Static model (no real-time drift handling)

---

## 🔮 Future Work

* Deep Learning (LSTM, Transformers)
* Real-time fraud detection systems
* Concept drift adaptation
* Fairness and bias analysis

---

## 📜 Research Paper

The full IEEE-style research paper is included in this repository.

---

## 👨‍💻 Author

**Kenish Hirpara**

---

## ⭐ Support

If you find this project useful, consider giving it a ⭐ on GitHub!
