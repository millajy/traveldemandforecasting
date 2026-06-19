# Travel Demand Forecasting Using SARIMA

Monthly international travel demand forecasting using historical data from Statistics Finland. I applied the Box-Jenkins methodology to build a SARIMA model that predicts the number of trips abroad taken by Finnish citizens.

The analysis covers January 2012 – December 2019 (pre-pandemic data only, to avoid structural breaks from COVID-19).

## What's in this repo

- `travel_forecast.ipynb` – full analysis and model development
- `Travel demand forecasting.pdf` – detailed write-up
- `trips-abroad.txt` – source dataset

## Approach

I worked through the standard Box-Jenkins workflow: visualizing the raw series, checking ACF/PACF plots, applying first-order and seasonal differencing, then estimating and diagnosing the model.

The final model is **SARIMA(0,1,0)(0,1,1)₁₂**, estimated via SARIMAX in Python.

## Results

| Metric | Value |
|--------|-------|
| MAE    | 94.3  |
| RMSE   | 114.9 |
| MAPE   | 11.0% |

The model captures the annual seasonal pattern well. Prediction intervals are fairly wide, which reflects the limits of a univariate model — adding external variables like economic indicators or fuel prices would likely improve accuracy.

## Stack

Python · Pandas · NumPy · Statsmodels · Matplotlib

