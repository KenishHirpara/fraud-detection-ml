# 💳 Advanced Credit Card Fraud Detection

### Controlled SMOTE • Cost-Sensitive Learning • Ensemble Models

---

## 📌 Overview

This project presents a **research-driven machine learning framework** for detecting fraudulent credit card transactions in highly imbalanced datasets.

Unlike traditional approaches that optimize accuracy, this work reframes fraud detection as an **Expected Risk Minimization problem**, where predictions are aligned with **real-world financial loss**.

---

## 🚀 Key Highlights

* 🔹 Controlled SMOTE (0.2 ratio) to avoid overfitting
* 🔹 Domain-driven Feature Engineering (Time + Log Scaling)
* 🔹 Cost-Sensitive Learning with asymmetric penalties
* 🔹 Ensemble Models: XGBoost, Random Forest, LightGBM
* 🔹 Evaluation using PR-AUC, ROC-AUC, F1-Score, and Financial Cost

---

## 📊 Dataset

Kaggle Dataset:
👉 https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

### 📌 Details

* Total Transactions: **284,807**
* Fraud Cases: **492 (~0.17%)**
* Features: **V1–V28 (PCA), Time, Amount**

⚠️ Dataset is not included due to size constraints.

---

## 🧠 Methodology

### 1. Feature Engineering

* Extracted temporal features (Hour, Is_Night)
* Applied log transformation on transaction amount
* Created relational features

---

### 2. Handling Class Imbalance

* Used **Controlled SMOTE (0.2)**
* Prevents synthetic overfitting

---

### 3. Models Used

* XGBoost (Best Model)
* Random Forest
* LightGBM
* Support Vector Machine
* Isolation Forest

---

### 4. Cost-Sensitive Evaluation

[
Cost = (FN \times 500) + (FP \times 10)
]

* False Negative → High loss
* False Positive → Low loss

---

## 📈 Results

| Model            | Precision | Recall    | F1 Score  | Cost ($) |
| ---------------- | --------- | --------- | --------- | -------- |
| Random Forest    | 1.000     | 0.714     | 0.833     | 1000     |
| **XGBoost**      | **0.857** | **0.857** | **0.857** | **510**  |
| LightGBM         | 0.714     | 0.714     | 0.714     | 1020     |
| SVM              | 0.833     | 0.714     | 0.769     | 1010     |
| Isolation Forest | 0.043     | 0.142     | 0.066     | 3220     |

🏆 **Best Model: XGBoost**

* Achieves optimal balance
* Reduces financial cost by **~49%**

---

## 📉 Visualizations

### ROC Curve

![ROC Curve](roc_curve.png)

### PR Curve

![PR Curve](pr_curve.png)

---

## ▶️ How to Run

```bash
git clone https://github.com/KenishHirpara/fraud-detection-ml.git
cd fraud-detection-ml
pip install -r requirements.txt
python model.py
```

⚠️ Replace `sample_data.csv` with full dataset for real results.

---

## 📁 Project Structure

```
fraud-detection-ml/
│
├── notebook.ipynb
├── model.py
├── requirements.txt
├── sample_data.csv
├── README.md
├── roc_curve.png
└── pr_curve.png
```

---

## 🧠 Research Insight

This project demonstrates that fraud detection should not be treated as a classification problem, but as an **asymmetric risk minimization problem**.

---

## ⚠️ Limitations

* PCA features reduce interpretability
* SMOTE introduces synthetic data
* Static model (no real-time drift handling)

---

## 🔮 Future Work

* LSTM / Transformer-based models
* Real-time fraud detection systems
* Concept drift adaptation
* Fairness and bias analysis

---

## 📜 Paper

The full research paper is included in this repository.

---

## 👨‍💻 Author

**Kenish Hirpara**
B.Tech Computer Science and Engineering
Karnavati University

---

## ⭐ Support

If you find this useful, give it a ⭐ on GitHub!
