# Walmart Sales Analysis and 12-Week Forecast

Analysis of weekly sales data from 45 Walmart stores using Python, covering what drives sales, which stores perform best and worst, and a 12-week sales forecast for every store.

## Problem
A retail chain with many outlets struggles to match inventory with demand. This project looks at what affects weekly sales and forecasts the next 12 weeks per store.

## Dataset
[Walmart Sales dataset on Kaggle](https://www.kaggle.com/datasets/mikhail1681/walmart-sales): 6,435 rows, 8 columns (Store, Date, Weekly_Sales, Holiday_Flag, Temperature, Fuel_Price, CPI, Unemployment).

## What I did
- Cleaned the data: converted dates, checked for missing values and duplicates
- Ranked stores by total sales and measured the gap between the best and worst store
- Checked how temperature, fuel price, CPI and unemployment relate to weekly sales, overall and per store
- Compared holiday weeks to normal weeks and looked at monthly seasonality
- Checked outliers with the IQR rule
- Forecast the next 12 weeks for each store with Holt-Winters exponential smoothing, tested on the last 12 weeks of known data

## Key findings
- **Best store:** Store 20. **Worst store:** Store 33. The best store sells about 8.11 x the worst.
- **Unemployment:** correlation with sales is -0.106176 overall. Stores most hurt: 38, 44, 39, 42 and 41.
- **Temperature:** correlation -0.063810 . **CPI:** -0.072634. **Fuel price:** 0.009464.
- **Holidays:** holiday weeks average 1.122888e+06 vs 1.041256e+06 for normal weeks.
- **Seasonality:** sales peak in November& December, likely due to Thanksgiving/Christmas shopping.
- **Outliers:** 34 unusually high weeks, mostly in November& December. I kept them because they are real holiday sales.
- **Forecast accuracy:** average error (0.0424) of 4% across stores on the last 12 weeks of data.

## Files
- `Walmart_Sales_Analysis_Forecast.ipynb`: full analysis and forecast
- `Walmart DataSet.csv`: dataset
- `forecast_12_weeks.csv`: forecast for each store

## How to run
1. Open the notebook in Google Colab
2. Upload `Walmart DataSet.csv`
3. Run all cells

## Tools
Python, Pandas, Matplotlib, Seaborn, Statsmodels, Scikit-learn

## Limitations and next steps
- The model uses sales history only; it does not use temperature, CPI or holiday flags
- Next step: try Prophet or a regression model that includes those features
