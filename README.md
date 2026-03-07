

# NYC Electricity Consumption Predictability

## Project Overview

This project implements a **Time Series Forecasting** model to predict electricity consumption in New York City using the **Facebook Prophet** module. The primary goal is to evaluate the predictability of energy demand across different temporal scales daily, monthly, and yearly while also exploring borough-specific consumption patterns.

## Key Objectives

* **Implement Prophet:** Utilize an additive model to fit non-linear trends with yearly, weekly, and daily seasonality.


* **Multi-Scale Testing:** Evaluate model performance on daily, monthly mean, and yearly mean datasets.


* **Model Tuning:** Experiment with linear and logistic growth settings and trend changepoints to optimize accuracy.


* **Borough Analysis:** Conduct a realistic analysis of electricity consumption across Manhattan, Brooklyn, Queens, Bronx, and Staten Island.



## Technical Stack

* **Language:** Python
* **Forecasting Engine:** `prophet` 


* **Data Manipulation:** `pandas`, `numpy` 


* **Visualization:** `matplotlib`, `seaborn` 


* **Evaluation:** `sklearn.metrics` (MAE, MAPE, $R^2$) 


* **Statistical Analysis:** `statsmodels` (for Autocorrelation Function analysis) 



## Data Preparation & Cleaning

Data was fetched directly from the **NYC OpenData API**. The cleaning process included:

* Handling missing values and converting date columns to datetime objects.


* Creating aggregated datasets for monthly and yearly means.


* Formatting data into the required `ds` (date) and `y` (target metric) columns for Prophet.



## Results & Model Performance

The model demonstrated varying levels of accuracy depending on the time unit. Notably, the **Yearly Mean** model achieved the highest $R^2$ value.

### Best Model for Each Time Unit

| Time Unit | Best Growth Model | Best Forecast Period | Best $R^2$ | Best MAPE |
| --- | --- | --- | --- | --- |
| **Daily** | Linear | 100 Days | 0.0026 | 19.32% |
| **Monthly** | Linear | 1 Month | 0.0658 | 6.74% |
| **Yearly** | Linear | 1 Year | 0.5111 | 1.21% |


### Borough Comparison Summary

Manhattan showed the highest average monthly consumption (6,595 kWh) and the highest annual growth rate (1.63%), while Staten Island recorded the lowest consumption (3,072 kWh).

## Limitations & Future Work

* **Model Constraints:** Current Prophet implementation assumes additive seasonality and does not yet include external regressors like temperature or COVID-19 anomalies.
* **Enhancements:** Future iterations aim to integrate **NOAA weather feeds** and explore ensemble methods with **SARIMA & LSTM**.

## Author

**Muhammad Ehtesham** 

---
