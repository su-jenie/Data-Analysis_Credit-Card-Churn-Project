# Credit Card Customer Churn Analysis

## Project Overview

This project analyzes credit card customer churn behavior and develops a machine learning model to predict churn probability.

Customers are segmented into risk tiers based on predicted churn probability and decision tree rules. The goal is to support effective customer retention strategies by identifying high-risk customers and understanding behavioral patterns across customer segments.

The analysis focuses on three key aspects of customer behavior:

- **Activity** (transaction behavior)
- **Trend** (recent behavioral changes)
- **Lock-in** (relationship strength)

---

## Dataset

Dataset: **BankChurners.csv**

The dataset contains information about credit card customers including:

- transaction activity
- account usage
- relationship with the bank
- demographic information

Target variable:
Attrited


- `1` = churned
- `0` = retained

---

## Project Workflow

1. Data preprocessing
2. Exploratory Data Analysis (EDA)
3. Feature engineering
4. Handling class imbalance
5. Model training
6. Model evaluation
7. Feature importance analysis
8. SHAP interpretation
9. Customer risk segmentation
10. Business strategy design

---

## Handling Class Imbalance

The dataset contains a significant class imbalance between churned and retained customers.

Therefore:

- **Accuracy was not used as the primary metric**
- **PR-AUC was used instead of ROC-AUC**

PR-AUC is more appropriate for evaluating models on imbalanced datasets.

---

## Models Compared

The following models were evaluated:

- Logistic Regression
- Random Forest
- LightGBM
- Linear SVM
- RBF SVM
- KNN
- CatBoost

Evaluation metrics:

- Precision
- Recall
- F1-score
- PR-AUC

---

## Final Model

**CatBoost**

Why CatBoost?

CatBoost handles categorical relationships effectively and showed the most stable performance across evaluation metrics, particularly in recall and precision balance under class imbalance.


---

## Customer Risk Segmentation

Customers were segmented into **five tiers** based on churn probability and behavioral rules derived from decision tree analysis.

| Tier | Description |
|-----|-------------|
| Tier 1 | Highest churn risk (urgent intervention required) |
| Tier 2 | High-risk monitoring group |
| Tier 3 | Growth potential customers |
| Tier 4 | High-value customers |
| Tier 5 | Loyal customers |

This segmentation enables targeted retention strategies.

---

## Key Analytical Techniques

- Feature importance analysis
- Decision tree rule extraction
- SHAP value interpretation
- Risk segmentation strategy
- Behavioral trend analysis

---

## Key Insights

- Transaction **frequency** was the strongest driver of churn.
- Customers with **high spending but low activity** showed high churn risk.
- Relationship strength significantly reduced churn probability.
- Early detection of inactivity signals is critical for retention.

---

## Business Strategy

Different retention strategies were designed for each tier.

Examples include:

- loyalty loop reinforcement for Tier 5
- VIP recognition strategies for Tier 4
- activity stabilization programs for Tier 3
- transaction recovery strategies for Tier 2
- immediate reactivation campaigns for Tier 1

---

## Visualization

The notebook includes visualizations using:

- Matplotlib
- Seaborn
- SHAP

---

## Requirements

Install required packages with:
pip install -r requirements.txt


---

## Author

**Sujin Heo**
