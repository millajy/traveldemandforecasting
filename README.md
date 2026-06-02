# Travel demand forecasting using SARIMA

## Overview

This project explores how seasonal time series forecasting can be used to predict monthly international travel demand. Using data from Statistics Finland, I developed and evaluated a Seasonal ARIMA (SARIMA) model to forecast the number of trips abroad taken by Finnish citizens.

The objective was to identify underlying trends and seasonal patterns in travel behavior and assess how accurately these patterns can be used to predict future travel volumes.

## Business Context

Accurate demand forecasting is important for industries such as tourism, transportation, and travel services, where staffing, capacity planning, and resource allocation depend on expected customer demand.

This project demonstrates a structured forecasting workflow, from exploratory analysis and model identification to evaluation and interpretation of forecast results.

## Dataset

**Source:** Statistics Finland

**Dataset:** Trips abroad, monthly (2012M01–2025M11)

**Variable used:** Monthly number of trips abroad by Finnish citizens (thousands of trips)

To avoid structural breaks caused by the COVID-19 pandemic, the analysis was restricted to observations from January 2012 to December 2019.

## Tools & Technologies

* Python
* Pandas
* NumPy
* Statsmodels
* Scikit-learn
* Matplotlib

## Methodology

### 1. Exploratory Analysis

The time series was visualized to identify trends and seasonal patterns.

Key observations:

* Slight upward long-term trend
* Strong annual seasonality
* Higher travel volumes during summer months
* Lower travel volumes during winter months

### 2. Model Identification

The Box-Jenkins methodology was used to identify an appropriate forecasting model.

Steps included:

* Autocorrelation (ACF) analysis
* Partial autocorrelation (PACF) analysis
* First-order differencing
* Seasonal differencing (lag = 12)

The analysis indicated that both trend and seasonality needed to be removed before model estimation.

### 3. Model Estimation

The final model selected was:

SARIMA(0,1,0)(0,1,1)₁₂

The model was estimated using maximum likelihood through the SARIMAX framework in Python.

### 4. Model Diagnostics

Residual diagnostics were performed to evaluate model adequacy:

* Residual plots
* Q-Q plot
* Residual autocorrelation analysis
* Ljung-Box tests

The model captured the majority of the systematic structure in the data, although some short-term residual autocorrelation remained.

### 5. Forecast Evaluation

The final 12 months of observations were reserved as a test set.

Forecast accuracy was evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Percentage Error (MAPE)

## Results

| Metric | Value |
| ------ | ----- |
| MAE    | 94.3  |
| RMSE   | 114.9 |
| MAPE   | 11.0% |

The model successfully captured the annual seasonal pattern of travel demand and produced reasonable short-term forecasts.

While the forecasts followed observed seasonal trends well, prediction intervals remained relatively wide, indicating uncertainty in future demand.

## Key Learnings

This project strengthened my understanding of:

* Time series analysis
* Forecasting methodologies
* SARIMA modeling
* Model diagnostics and validation
* Forecast accuracy evaluation
* Communicating analytical findings

It also highlighted the limitations of purely univariate forecasting models and the potential value of incorporating external variables such as economic indicators, fuel prices, or policy changes.

## Future Improvements

Potential extensions include:

* Comparing multiple forecasting approaches
* Testing SARIMA models with additional autoregressive components
* Incorporating external explanatory variables (SARIMAX)
* Comparing performance against Prophet or machine learning-based forecasting methods

## Repository Contents

* `travel_forecast.ipynb` – analysis and model development
* `Project report.pdf` – detailed project report
* `data/` – source dataset
* `figures/` – visualizations and forecast outputs

## Author

Milla Jylänki

M.Sc. Student in Information and Service Management
Aalto University
