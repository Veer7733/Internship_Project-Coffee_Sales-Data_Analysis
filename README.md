# Internship_Project-Coffee_Sales-Data_Analysis

A data-driven analysis and machine learning project focused on understanding coffee purchasing patterns and predicting transaction spend using historical vending machine sales data. The project uncovers customer behavior trends across time, product types, and payment modes, and uses predictive modeling to support actionable business decisions.

---

## Project Overview

This project analyzes **1,133 coffee vending transactions** from **March to July 2024** and builds machine learning models to predict **money spent per transaction**. By performing extensive EDA and feature engineering, the project aims to generate insights that can help optimize **inventory planning, vending machine restocking, demand forecasting, and pricing strategies**.

---

## Data Summary

| Feature | Description |
|--------|-------------|
| `date`, `datetime` | Transaction date & timestamp |
| `cash_type` | Payment type (`card` or `cash`) |
| `card` | Customer ID (for card payments) |
| `coffee_name` | Type of coffee purchased |
| `money` | Amount spent per transaction |

- **Timeframe:** 01 March 2024 – 31 July 2024  
- **Total Records:** 1,133  
- **~92% card payments**, indicating preference for digital transactions.

---

## Key Business Insights

### Coffee Preference Insights
| Coffee Type | Quantity Sold | Total Revenue |
|--------------|--------------|---------------|
| **Americano with Milk** | 268 | 8601.94 |
| **Latte** | 243 | **9009.14** ✔ Highest revenue |
| Cappuccino | 196 | 7333.14 |
| Americano | 169 | 4644.54 |

- *Latte is most profitable*, although Americano with Milk has slightly higher sales volume.
- *Cocoa and Espresso show low demand.*

### Time-based Trends
- **Peak month:** **May** → *Highest sales & quantity*
- **Peak hours:** *Morning (10 AM) and Evening (7–8 PM)*
- **More sales on weekends & month-end**
- Suggests restocking should **increase before month-end and during peak hour windows**

### Payment Patterns
- **Card transactions dominate (92%)** → Deployment of UPI/contactless payments highly beneficial
- Cash transactions lower (~8%), likely due to convenience factors

---

## Methodology

### 1️. Data Cleaning & Preparation
- Checked for duplicates (none found)
- Treated missing values (89 null in `card` column → all cash transactions)
- Converted datetime fields
- Extracted features: `year`, `month`, `day`, `hour`

### 2️. Feature Engineering
- Removed unused columns: `date`, `datetime`, `card`, `year`
- One-hot encoded `coffee_name`, `cash_type`
- Standardized numerical features

### 3️. ML Modeling
- Target Variable: `money`
- **Train / Test Split:** 80% / 20%  
- Models used:
  - Linear Regression
  - Random Forest Regressor

---

## Model Performance

| Metric | Linear Regression | Random Forest |
|--------|------------------|---------------|
| **R² Score** | 0.9470 | **0.9929** 🔥 |
| RMSE | 1.1593 | **0.4232** |
| MSE | 1.3440 | **0.1791** |
| MAE | 0.9598 | **0.0869** |

✔ **Best Model:** *Random Forest Regressor* — suitable for non-linear consumer purchase behavior

---

## Recommendations

| Actionable Strategy | Impact |
|--------------------|--------|
| Stock more **Latte & Americano with Milk** | Increased revenue |
| Schedule inventory updates during **peak times & month-end** | Prevent stock-outs |
| Promote **digital payment options** | Customer convenience |
| Introduce **discount campaigns for low-selling items** | Increase sales of Espresso & Cocoa |
| Consider **seasonal demand (May surge)** | Optimized supply planning |

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Programming | Python |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| ML Modeling | Scikit-learn |
| Notebook | Jupyter |

---

##  How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/Veer7733/Internship_Project-Coffee_Sales-Data_Analysis
   ``` 
2. Navigate to the project folder:
   ```bash
   cd Internship_Project-Coffee_Sales-Data_Analysis
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```
4. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Coffee_Sales_DA.ipynb
   ```


