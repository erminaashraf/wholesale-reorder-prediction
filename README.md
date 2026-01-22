# Customer-SKU Reorder Prediction in Wholesale

Predictive analytics project using transaction data from a UK-based wholesale retailer to model whether a customer will reorder a specific SKU within 42 days.

## Project Overview
This project investigates whether customer reorder behaviour exhibits predictable patterns across time, seasonality, product characteristics, and customer segments. The goal is to support smarter inventory planning, replenishment, and operational decision-making.

The dataset contains transactional data from a UK-based giftware wholesaler (2009–2011).

## Problem Definition
We predict whether a customer will reorder a given SKU within **42 days**, where 42 days represents the median inter-purchase interval observed in the data.

## Methods Used
Three models were developed:

### Model 1 — Logistic Regression (Baseline)
Features:
- Price  
- Country  
- Holidays  

Performance:
- ROC-AUC: **0.531**  
→ Weak predictive power, close to random.

---

### Model 2 — Logistic Regression + Feature Engineering
Added features:
- Prior purchase within the window  
- Monthly indicators (seasonality)

Improvements:
- ROC-AUC increased to **0.658**
- October & November increased reorder likelihood by over **200%**
- Prior purchase increased reorder probability by **72%**

---

### Model 3 — Logistic Regression + Customer Segmentation
Added customer-level clusters using **K-Means (K=4)** based on:
- Total spend  
- Quantity purchased  
- Number of invoices  
- Number of unique SKUs  

Findings:
- Large wholesalers and specialty retailers had significantly higher reorder likelihood
- Model performance improved further:
  - ROC-AUC: **0.677**
  - Better balance between sensitivity and specificity

---

## Key Insights
- Reorder behaviour is **not random**
- Strongest predictors:
  - Prior purchase behaviour  
  - Seasonality (Oct–Nov peak)  
  - Price  
  - Customer segment  
- Customer segmentation improves model realism and operational usefulness

---

## Tools Used
- Python  
- Pandas / NumPy  
- Scikit-learn  
- Logistic Regression  
- K-Means Clustering  
- Matplotlib / Seaborn  
- Jupyter Notebook  

---

## Business Applications
This model can support:
- Inventory planning  
- Demand forecasting  
- SKU prioritization  
- Seasonal stock adjustment  
- Customer-specific service levels  

---

## Dataset
Online Retail II dataset (UCI Machine Learning Repository):
http://archive.ics.uci.edu/dataset/502/online+retail+ii

The dataset used in this project is not included in the repository due to size constraints.


---

## Notes
This project was completed as part of MGSC 401 – Statistical Foundations of Data Analytics.
