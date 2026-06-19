# Credit Card Fraud Detection using Machine Learning

A machine learning project focused on detecting fraudulent credit card transactions. This project evaluates multiple approaches, moving from traditional linear models to advanced ensemble methods, to solve a massive real-world banking challenge.

---

## 🌍 Real-World Context

In the banking and financial sector, credit card fraud costs financial institutions and consumers billions of dollars annually. As payment systems move completely digital, fraudulent tactics become increasingly fast and sophisticated. 

However, banks face a major operational paradox: **they must protect their revenue without ruining the customer experience.** 

---

## 🛑 The Problem

When analyzing transaction data to catch fraud, data scientists face a massive technical hurdle: **extreme class imbalance**. In a typical banking dataset, legitimate transactions make up over 99.9% of the data, while fraud represents a tiny fraction of a percent.

If a machine learning model is trained poorly on this data, the consequences are severe for a bank:

* **High False Negatives (Missed Frauds):** The bank suffers direct financial losses and legal liabilities, while criminal networks succeed.
* **High False Positives (False Alarms):** Honest customers have their credit cards blocked at the store checkout. This causes extreme user frustration, harms the bank's reputation, and overloads customer support call centers with complaints.

---

## 🛠️ My work

In this project, I engineered and evaluated **4 different modeling strategies** using a standard credit card dataset (containing anonymized PCA features due to strict banking confidentiality):

1. **Feature Engineering:** Implemented data splitting strategies (`stratify=y`) and mathematical transformations (`log1p` on transaction amounts) to handle skewed distributions.
2. **Model Exploration:** Developed and compared baseline linear models (**Logistic Regression**) against advanced tree-based ensemble methods (**Random Forest**).
3. **Handling Imbalance:** Tested the algorithms directly on the **unbalanced** dataset to evaluate how inherently robust non-linear models are compared to strict linear boundaries.

---

## 💡 The Proposed Solution (Model 4)

The definitive solution proposed in this project is **Model 4 (Random Forest Classifier on Unbalanced Data)**. 

### Key Performance Metrics (Out of 56,962 test transactions)
* **Fraud Detection Rate (Recall):** **82%** (Intercepted 80 out of 98 actual frauds).
* **Alert Reliability (Precision):** **94%** (When the model alerts, it is correct 94% of the time).
* **Operational Impact:** **Only 5 False Alarms** out of nearly 57,000 genuine transactions.

### Why it works
Instead of trying to draw a simplistic straight line through the data, the Random Forest aggregates votes from hundreds of independent decision trees. It automatically identifies complex, non-linear rules based on behavioral patterns hidden within the top anonymized criteria (**V17, V14, and V12**), capturing fraud with surgical precision.

---

## 📂 Project Structure

* `Credit Card Fraud Detection.ipynb`: The complete Jupyter notebook containing data preprocessing, model training, evaluation metrics, and feature importance analysis.
* `README.md`: Project summary and business context.
