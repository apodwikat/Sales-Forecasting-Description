# Sales-Forecasting-Description
Python, Pandas, Matplotlib, Scikit-learn. Time series forecasting  | Regression

### Author: Eng. Abdallah Dwikat
### Organization: Elevvopath Intern
### Date: 28th of August 2025

This project focuses on analyzing and forecasting Walmart weekly sales using historical data. The analysis includes exploratory data analysis (EDA), statistical testing, feature engineering, and regression-based forecasting.

Goals of the Repository

Predict future sales using historical weekly data

Create time-based features (day, month, week, lag values)

Apply regression models (Linear Regression, XGBoost, LightGBM) to forecast next period’s sales

Visualize actual vs. predicted values to assess accuracy

Dataset Overview

File: Walmart DataSet.csv
Rows: ~6,435 (reduced to ~5,920 after outlier removal)
Columns:

Store – Store ID (1–45)

Date – Week of observation

Weekly_Sales – Total sales for that store and week

Holiday_Flag – 1 if the week includes a holiday, else 0

Temperature – Temperature in the region (°F)

Fuel_Price – Fuel price in the region

CPI – Consumer Price Index

Unemployment – Regional unemployment rate

No missing values were found.

Implementation Details
# 1. Imports

Key libraries used:

Data manipulation: pandas, numpy

Visualization: matplotlib, seaborn

Statistical analysis: scipy, statsmodels

Feature engineering and ML: sklearn, xgboost, lightgbm

# 2. Data Cleaning

Converted Date column to datetime format

Set Date as index for time-series operations

Removed outliers from Weekly_Sales and Unemployment using IQR filtering

# 3. Exploratory Data Analysis (EDA)

Boxplots of all numeric columns to detect outliers

Trend plots of Weekly_Sales to check for seasonality

Seasonal decomposition with a 52-week period

Kruskal-Wallis test confirming statistically significant seasonality

Key findings:

Seasonal spikes in early months (likely New Year impact)

No strong correlation between Weekly_Sales and Temperature (r ≈ –0.04)

Weak negative correlation with CPI overall (r ≈ –0.08), though some stores are strongly affected

# 4. Statistical Data Analysis

Store-level correlations with Unemployment and CPI to find the most affected stores

Top-performing stores identified by total historical sales (Store 20 highest, Store 38 lowest)

Large disparity between best and worst performing stores

# 5. Seasonality and Store-Level Insights

Decomposed Weekly_Sales for Store 22 as an example → clear annual patterns

Top 5 performing stores: 20, 14, 2, 13, 10

Worst performing store: 38 (sales gap vs. Store 20 is significant: >270M USD difference)

Visualizations

Boxplots: Outlier detection for all numeric features

Time-series plots: Weekly sales trends (all stores, and individual stores)

Seasonal decomposition: Overall data and per-store sales

Correlation heatmaps: Weekly sales vs. macroeconomic indicators

# Requirements

Install dependencies using pip:

pip install pandas numpy matplotlib seaborn scipy scikit-learn xgboost lightgbm statsmodels

How to Run

Download Walmart DataSet.csv

Update dataset path in the script:

df = pd.read_csv(r"C:\Users\hp\Elevvopath\7) Sales_Forecasting_Description\Walmart DataSet.csv")


Execute the Python notebook or script step by step to:

Clean and analyze the data

Visualize trends and seasonality

Train regression models (Linear Regression, XGBRegressor, LGBMRegressor)

Plot actual vs. predicted sales

## Key Insights

Seasonality confirmed → sales spike around New Year

Minimal effect from Temperature and Unemployment overall

CPI affects certain stores strongly (positive and negative correlations)

Store-level disparities are substantial → top stores generate >30× sales of lowest performers

# Future Enhancements

Add lag features and rolling statistics for improved forecasting accuracy

Use Prophet or ARIMA for more advanced time-series modeling

Incorporate holiday events and markdown data for better predictions

Automate store-wise forecasting dashboards

Walmart Sales Forecasting completed successfully!
Seasonality and store-level patterns were identified, laying the foundation for predictive modeling.

## Author: Eng. Abdallah Dwikat
## Date: 28th of August 2025
