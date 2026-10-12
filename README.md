# NYC Electricity Consumption Forecasting with Prophet

How predictable is New York City's electricity use? This project fits Facebook Prophet to NYC consumption data at daily, monthly and yearly resolution, tunes the growth model and changepoints, and compares the five boroughs.

## Data

NYC electric consumption records pulled from the NYC Open Data API, cleaned (missing values, date parsing) and aggregated to daily, monthly-mean and yearly-mean series in Prophet's `ds` / `y` format.

## Method

- Prophet's additive model with yearly, weekly and daily seasonality
- Linear and logistic growth, several changepoint settings, several forecast horizons
- Evaluation with MAE, MAPE and R²; autocorrelation checked with `statsmodels`

## Results

| Time unit | Best growth model | Best horizon | R² | MAPE |
|---|---|---|---:|---:|
| Daily | Linear | 100 days | 0.003 | 19.32% |
| Monthly | Linear | 1 month | 0.066 | 6.74% |
| Yearly | Linear | 1 year | 0.511 | 1.21% |

- Daily consumption is close to unpredictable from its own history alone (R² near zero). Aggregating removes noise, and the yearly series is far more predictable.
- **Manhattan** uses the most electricity (6,595 kWh average per month) and is growing fastest (1.63% a year). **Staten Island** uses the least (3,072 kWh).

## Limitations and next steps

- The model uses only past consumption. Adding temperature from NOAA weather data should help the daily forecasts most.
- COVID-19 years are not treated as special periods.
- SARIMA and LSTM models are the next comparison.

## Files

| File | Contents |
|---|---|
| `NYC_Electricity_consumtion_predictibility_usiny_FBProphet2---.ipynb` | Data pull, cleaning, models and evaluation |
| `NYC Electricity Consumption Predictability.pptx` | Presentation of results |

## How to run

```bash
git clone https://github.com/mehtesham13/Time-Series-Forecasting-using-Facebook-Prophet.git
cd Time-Series-Forecasting-using-Facebook-Prophet
pip install prophet pandas numpy matplotlib seaborn scikit-learn statsmodels
jupyter notebook
```

Author: Muhammad Ehtesham · [LinkedIn](https://www.linkedin.com/in/muhammad-ehtesham-dsa)
