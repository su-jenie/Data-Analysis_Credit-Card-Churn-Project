# Credit Card Customer Churn Analysis

## Project Overview

This project analyzes credit card customer churn behavior and develops a machine learning model to predict churn probability.

Beyond prediction, customers are segmented into risk tiers based on predicted churn probability and decision tree rules. The goal is to support more effective customer retention strategies by identifying high-risk customers early and understanding the behavioral patterns associated with churn.

The analysis focuses on three key aspects of customer behavior:

- **Activity**: how actively customers use their credit cards
- **Trend**: how customer behavior is changing over time
- **Lock-in**: how strongly customers are tied to the bank relationship

This project was conducted as part of a data analytics bootcamp and combines predictive modeling with business-oriented customer segmentation.

---

## Business Problem

Customer churn is a critical issue for credit card companies because losing an existing customer is often more costly than retaining one.

To improve retention, financial institutions need to answer questions such as:

- Which customers are most likely to churn?
- What behavioral patterns are associated with churn?
- Which customers require immediate intervention?
- How should retention strategies differ across customer groups?

This project addresses those questions by building a churn prediction model and translating model outputs into actionable customer risk tiers.

---

## Dataset

Dataset: **BankChurners.csv**

Source: Kaggle  
https://www.kaggle.com/datasets/gonieahn/zero-base-project-creditcard-analysis

The dataset contains information about credit card customers, including:

- transaction activity
- account usage
- relationship with the bank
- demographic information

### Target Variable

**Attrited**

- `1` = churned
- `0` = retained

---

## Key Questions

This project explores the following questions:

1. What behavioral patterns distinguish churned customers from retained customers?
2. Which features are the strongest drivers of churn?
3. How can churn probability be predicted effectively under class imbalance?
4. How can predicted risk be translated into actionable customer segments?
5. What retention strategies should be prioritized for different customer groups?

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

## Exploratory Data Analysis

EDA was conducted to understand the differences between churned and retained customers across multiple dimensions.

The analysis focused on:

- transaction frequency
- transaction amount
- revolving balance behavior
- relationship length
- product usage
- customer demographics

This step helped identify early signals of churn and guided subsequent feature engineering and model design.

---

## Feature Engineering

To better capture customer churn behavior, features were designed around three behavioral dimensions:

### 1. Activity
Indicators of how actively customers use their accounts, such as transaction count and transaction amount.

### 2. Trend
Indicators of recent behavioral decline or change, which may signal disengagement before churn.

### 3. Lock-in
Indicators of relationship strength, such as tenure and product-related engagement, which may reduce churn risk.

This framework helped structure the analysis in a business-interpretable way rather than relying only on raw variables.

---

## Handling Class Imbalance

The dataset contains a significant class imbalance between churned and retained customers.

Therefore:

- **Accuracy was not used as the primary metric**
- **PR-AUC was prioritized over ROC-AUC**

PR-AUC is more appropriate for imbalanced classification problems because it better reflects performance on the minority class.

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

### Evaluation Metrics

- Precision
- Recall
- F1-score
- PR-AUC

These models were compared to identify the most effective approach for detecting churn risk while maintaining interpretability and business usefulness.

---

## Final Model

**CatBoost**

### Why CatBoost?

CatBoost showed the most stable overall performance across evaluation metrics and performed particularly well in balancing precision and recall under class imbalance.

It was selected as the final model because it provided strong predictive performance while also supporting downstream interpretation and segmentation work.

---

## Model Interpretation

To make the model results actionable, the project included multiple interpretation methods:

- **Feature importance analysis** to identify major churn drivers
- **Decision tree rule extraction** to derive interpretable segmentation logic
- **SHAP value analysis** to understand how individual features influenced churn probability

These methods helped bridge the gap between model performance and business decision-making.

---

## Customer Risk Segmentation

Customers were segmented into **five tiers** based on churn probability and behavioral rules derived from decision tree analysis.

| Tier | Description |
|------|-------------|
| Tier 1 | Highest churn risk (urgent intervention required) |
| Tier 2 | High-risk monitoring group |
| Tier 3 | Growth potential customers |
| Tier 4 | High-value customers |
| Tier 5 | Loyal customers |

This segmentation allows the business to move from simple prediction to targeted customer management.

---

## Key Insights

The analysis produced several important insights:

- Transaction **frequency** was one of the strongest drivers of churn.
- Customers with **high spending but low activity** showed elevated churn risk.
- Stronger relationship indicators reduced churn probability.
- Changes in recent behavior were often more informative than static customer attributes.
- Early detection of inactivity signals is critical for retention strategy.

---

## Business Strategy

Different retention strategies were designed for each customer tier.

Examples include:

- **Tier 5**: loyalty loop reinforcement
- **Tier 4**: VIP recognition and relationship strengthening
- **Tier 3**: activity stabilization and engagement support
- **Tier 2**: transaction recovery and risk monitoring
- **Tier 1**: immediate reactivation campaigns

This makes the project more than a churn prediction exercise; it connects analytical results to practical business action.

---

## Tech Stack

Python libraries used in this project:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- catboost
- shap

---

## Repository Structure

```bash
credit-card-customer-churn-analysis
│
├── notebook
│   └── Credit_Card_Analysis_Sujin_Eng.ipynb
│
├── data
│   └── BankChurners.csv
│
├── requirements.txt
│
└── README.md
```

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/su-jenie/Data-Analysis_Credit-Card-Churn-Project.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
notebook/Credit_Card_Analysis_Sujin_Eng.ipynb
```

The analysis can be run in:

- Jupyter Notebook
- Google Colab

---

## Visualization

The notebook includes visualizations and interpretation outputs using:

- Matplotlib
- Seaborn
- SHAP

These visualizations support both model evaluation and business interpretation.

---

## Author

**Sujin Heo**