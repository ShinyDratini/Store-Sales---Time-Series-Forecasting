# Store-Sales---Time-Series-Forecasting
# Retail Demand Forecasting Using XGBoost

## Project Overview

This project uses machine learning and time-series forecasting techniques to predict daily sales for a large Ecuadorian grocery retailer based on the Kaggle Store Sales Forecasting dataset.

The objective is to improve demand planning and inventory management by forecasting future sales using historical demand patterns, seasonality, and business events. Accurate forecasts can help retailers optimize inventory levels, reduce stockouts, and improve customer service.

Dataset Source:
https://www.kaggle.com/competitions/store-sales-time-series-forecasting

---

## Business Problem

Retailers must accurately forecast demand to:

* Reduce stock shortages
* Minimize excess inventory
* Improve replenishment planning
* Support data-driven decision making

This project focuses on forecasting daily sales for the **GROCERY I** product family at **Store 44**, the highest-performing store in the dataset.

---

## Dataset

The dataset contains over 3 million sales records and includes:

* Historical sales transactions
* Product families
* Store information
* Promotional activities
* Holiday and event calendars
* Oil prices
* Customer transaction counts

Key Findings from Exploratory Data Analysis:

* GROCERY I was the largest sales contributor, generating over 343 million in sales.
* Store 44 was the top-performing store with over 62 million in total sales.
* Approximately 31% of observations recorded zero sales, indicating intermittent demand patterns common in retail environments.

---

## Data Preparation & Feature Engineering

The following forecasting features were created:

### Lag Features

* Lag 7
* Lag 14
* Lag 28

### Rolling Statistics

* Rolling 7-Day Average
* Rolling 30-Day Average

### Calendar Features

* Day of Week
* Month
* Day of Month

### Business Features

* Holiday Indicator

These features allow the model to capture seasonality, historical demand patterns, and business events.

---

## Model Development

### Algorithm

XGBoost Regressor

### Train-Test Strategy

A time-based split was used to preserve chronological order and prevent data leakage.

* Training Set: 80%
* Testing Set: 20%

---

## Model Performance

| Metric | Result |
| ------ | ------ |
| MAE    | 1,552  |
| RMSE   | 2,353  |
| R²     | 0.576  |

### Interpretation

The model successfully captured recurring weekly demand patterns and explained approximately 57.6% of the variation in sales.

While regular demand cycles were forecasted effectively, sudden demand spikes and anomalies remain challenging to predict and could potentially be improved through additional features such as promotions and customer transaction volume.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-Learn
* XGBoost
* Jupyter Notebook

---

## Project Structure

```text
retail-demand-forecasting/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_xgboost_forecasting.ipynb
│
├── screenshots/
│   ├── sales_trend.png
│   ├── forecast_vs_actual.png
│
├── README.md
└── requirements.txt
```

---

## Future Enhancements

Planned improvements include:

* Incorporating promotional activity data
* Adding customer transaction volume
* Incorporating oil price information
* Hyperparameter optimization
* Safety stock and reorder point calculations
* Interactive Streamlit dashboard for demand planning

---

## Business Application

This solution demonstrates how machine learning can support supply chain and retail planning functions by:

* Forecasting future demand
* Improving inventory planning
* Supporting replenishment decisions
* Reducing stockout risk
* Enhancing operational efficiency
