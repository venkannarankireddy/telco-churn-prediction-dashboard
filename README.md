# Telco Customer Churn Prediction & Dashboard

End-to-end churn analysis on 7,043 telecom customers: a Python ML model that scores each customer's churn risk, plus an interactive Tableau dashboard.

**Live dashboard:** [View on Tableau Public]https://public.tableau.com/app/profile/rankireddy.venkanna.babu/viz/Telecom_Customer_Churn_Analysis_17924107795680/TelecomChurnDashboard?publish=yes

![Dashboard](images/dashboard.png)

## Business Problem
Which customers are leaving, why, and who is most at risk next?

## Dataset
[Telco Customer Churn (Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn): 7,043 customers, 21 columns.

## Approach
1. **Cleaning:** fixed blank `TotalCharges` values (11 new customers with 0 tenure) and created tenure groups and a churn flag.
2. **Modeling:** trained Logistic Regression and Random Forest (balanced class weights, stratified split).
3. **Risk scoring:** used 5-fold cross-validated probabilities for all customers and grouped them into Low, Medium, and High risk.
4. **Dashboard:** built KPIs, churn breakdowns, filters, click actions, and a high-risk customer list in Tableau.

## Results
- Overall churn rate: **26.5%**
- ROC-AUC: **0.84** (Logistic Regression 0.841, Random Forest 0.844)
- Actual churn by risk level: **High 69.1%**, Medium 37.7%, Low 8.6%
- Key drivers: month-to-month contracts (42.7% churn), fiber optic internet (41.9%), first-year customers (47.4%)
- **1,266 high-risk customers**, about **$99K in monthly revenue at risk**

## Tools
Python (pandas, scikit-learn), Google Colab, Tableau

## Files
- `churn_analysis_and_model.ipynb`: data cleaning and modeling
- `data/telco_final.csv`: cleaned data with churn probabilities and risk levels
- `images/dashboard.png`: dashboard screenshot
