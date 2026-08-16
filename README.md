# Customer Retention Analytics Engine

## Overview

This project uses customer data from a telecommunications company to identify customers at risk of churn and translate the predictions into actionable retention insights.

The project combines machine learning, business analysis, and Power BI reporting to help a retention team answer:

- Which customers are predicted to churn?
- Which customer segments show the greatest churn risk?
- How much monthly recurring revenue is at risk?
- How well does the prediction model identify actual churners?

## Business Problem

Customer churn reduces monthly recurring revenue and increases the cost of acquiring replacement customers. The objective of this project is to identify likely churners so that the business can prioritise retention campaigns, especially for high-value customers.

## Tools Used

- Python: Pandas, NumPy, Scikit-learn
- Power BI: interactive dashboard and DAX measures
- Jupyter Notebook: data preparation and model development
- GitHub: version control and project documentation

## Dataset

- Dataset: IBM Telco Customer Churn
- Source: Kaggle / IBM Watson Analytics
- Target variable: `Churn`
- Key features: contract type, internet service, tenure, monthly charges, total charges, payment method, and service subscriptions

## Project Workflow

```text
Telco Customer Churn Data
        ↓
Data Cleaning and Transformation
        ↓
Feature Encoding
        ↓
Train/Test Split
        ↓
Random Forest Classification Model
        ↓
Holdout Prediction Evaluation
        ↓
Power BI Retention Dashboard
        ↓
Business Insights and Retention Actions
```

## Machine Learning Model

A Random Forest classifier was trained to predict whether a customer would churn.

The dashboard evaluates model predictions against actual churn outcomes from the holdout test dataset.

### Model Performance

| Metric | Result |
|---|---:|
| Accuracy | 78.54% |
| Precision | 62.68% |
| Recall | 47.59% |
| True Positives | 178 |
| True Negatives | 927 |
| False Positives | 106 |
| False Negatives | 196 |

### Interpretation

The model correctly classifies 78.54% of customers overall. However, recall is 47.59%, meaning the model identifies 178 of 374 customers who actually churned.

This model should therefore be treated as a baseline prioritisation tool rather than a fully automated retention decision system. Improving recall is an important next step because missed churners may represent lost recurring revenue.

## Power BI Dashboard

The Power BI report contains two pages.

### 1. Customer Retention Overview

The dashboard includes:

- Total customers
- Predicted churners
- Actual churners
- Predicted churn rate
- Monthly revenue at risk
- Predicted churners by contract type
- Predicted churners by internet service
- Predicted churners by customer tenure group
- Interactive slicers for contract type, internet service, and tenure
- An action table showing customers predicted to churn

### 2. Model Performance

The model performance page includes:

- Accuracy
- Precision
- Recall
- Confusion matrix comparing actual churn against predicted churn

## Key Dashboard Findings

- Total customers evaluated: 1,407
- Customers predicted to churn: 284
- Actual churners: 374
- Predicted churn rate: 20.18%
- Monthly revenue at risk: approximately $21,695
- Month-to-month customers represent the largest predicted churn segment.
- Fiber optic customers represent the largest predicted churn segment by internet service.
- Customers with 0–12 months of tenure represent the largest predicted churn group.

## Business Recommendations

1. Prioritise month-to-month customers for retention campaigns.
2. Target high-value customers predicted to churn, beginning with those with the highest monthly charges.
3. Offer incentives such as contract upgrades, service bundles, or targeted discounts.
4. Focus onboarding and engagement efforts on customers in their first 12 months.
5. Improve the model by testing class balancing, probability thresholds, and additional classification algorithms.

## Future Improvements

- Use predicted churn probabilities instead of only binary predictions.
- Tune the classification threshold to improve churn recall.
- Compare Logistic Regression, Random Forest, and Gradient Boosting models.
- Add precision-recall and ROC-AUC evaluation.
- Introduce retention-campaign outcome tracking to measure realised ROI.
- Refresh the dashboard with newly scored customer data.

## Repository Structure

```text
dashboard/     Power BI dashboard file
data/          Dashboard-ready model prediction data
notebooks/     Python notebook for cleaning, modelling, and evaluation
assets/        Dashboard screenshots
README.md      Project documentation
```

## Dashboard Preview

Add screenshots to the `assets` folder, then display them here:

```markdown
![Customer Retention Dashboard](assets/dashboard-overview.png)

![Model Performance Dashboard](assets/model-performance.png)
```

## Author

Sharath C  
Business Analyst / Engineering Student  
GitHub: [06SharXD](https://github.com/06SharXD)
