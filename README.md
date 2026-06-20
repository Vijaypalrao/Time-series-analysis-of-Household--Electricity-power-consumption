# Household Electricity Consumption Forecasting Using ARIMA and SARIMA and some Deep learning models and ML models
# Seasonal Electricity Consumption Analysis and Forecasting

## Project Overview

Electricity consumption forecasting plays a critical role in energy management, demand planning, and efficient resource allocation. Household electricity usage exhibits complex temporal patterns influenced by daily routines, seasonal variations, and changing consumption behavior.

This project focuses on analyzing and forecasting household electricity consumption using classical time series techniques. The study explores trend, seasonality, stationarity, and temporal dependencies in electricity usage and develops forecasting models using ARIMA and SARIMA.

The target variable used in this project is:

**Global Active Power (kW)**

---

## Problem Statement

Develop a robust time series forecasting framework to analyze and predict household electricity consumption patterns while capturing trend, seasonality, and temporal dependencies using statistical forecasting models.

---

## Dataset

**Household Power Consumption Dataset**

The dataset contains household electricity usage measurements collected over time and includes variables such as:

- Global Active Power
- Global Reactive Power
- Voltage
- Global Intensity
- Sub Metering 1
- Sub Metering 2
- Sub Metering 3

Target Variable:

```text
Global Active Power (kW)
```

---

## Project Workflow

### 1. Data Preprocessing

- Date-Time conversion
- Datetime index creation
- Data type conversion
- Missing value handling
- Time-based interpolation
- Forward Fill and Backward Fill

---

### 2. Exploratory Data Analysis (EDA)

Performed comprehensive exploratory analysis including:

- Summary Statistics
- Missing Value Analysis
- Distribution Analysis
- Histogram
- KDE Plot
- Boxplots
- Correlation Heatmap
- Consumption Trend Visualization

---

### 3. Time Series Construction

Electricity consumption was aggregated into:

- Hourly Time Series
- Daily Time Series
- Weekly Time Series
- Monthly Time Series

---

### 4. Stationarity Analysis

Stationarity was evaluated using the Augmented Dickey-Fuller (ADF) Test.

#### ADF Results

| Time Series | Result |
|-------------|---------|
| Hourly | Stationary |
| Daily | Non-Stationary |
| Weekly | Stationary |
| Monthly | Non-Stationary |

The hourly time series was selected for forecasting due to:

- Highest temporal resolution
- Maximum information retention
- Strong seasonal characteristics

---

### 5. Seasonality Analysis

Seasonality was investigated using:

- Hour of Day Consumption Pattern
- Seasonal Decomposition
- Seasonal Autocorrelation Function (ACF)

Key findings:

- Strong daily seasonal pattern detected
- Significant spikes observed at seasonal lags
- Seasonal period identified as:

```text
s = 24 Hours
```

---

### 6. ARIMA Modeling

Classical ARIMA models were developed after stationarity verification.

#### Steps

- ADF Test
- ACF Analysis
- PACF Analysis
- Candidate Model Selection
- Model Comparison using AIC/BIC
- Residual Diagnostics
- Forecast Generation

#### Candidate ARIMA Models

```text
ARIMA(1,0,0)
ARIMA(0,0,1)
ARIMA(1,0,1)
ARIMA(2,0,0)
ARIMA(2,0,1)
ARIMA(2,0,2)
ARIMA(3,0,1)
ARIMA(3,0,2)
ARIMA(3,0,3)
ARIMA(4,0,1)
```

#### Model Evaluation

- AIC
- BIC
- Residual Analysis
- Q-Q Plot
- Forecast Plot
- Confidence Intervals

---

### 7. Train-Test Validation

The forecasting performance was validated using chronological train-test splitting.

#### Method

```text
80% Training Data
20% Testing Data
```

#### Evaluation Metrics

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- MAPE (Mean Absolute Percentage Error)

#### Validation Outputs

- Actual vs Predicted Plot
- Zoomed Forecast Plot
- Confidence Interval Plot
- Residual Diagnostics

---

### 8. SARIMA Modeling

To capture the identified seasonal structure, Seasonal ARIMA models were developed.

Seasonal period:

```text
s = 24
```

#### SARIMA Framework

```text
SARIMA(p,d,q)(P,D,Q,24)
```

#### Steps

- Seasonal ACF Analysis
- Seasonal Decomposition
- Candidate SARIMA Models
- AIC/BIC Comparison
- Best Model Selection
- Residual Diagnostics
- Forecasting
- Confidence Interval Analysis

#### Candidate SARIMA Models

```text
SARIMA(1,0,1)(1,0,1,24)
SARIMA(2,0,1)(1,0,0,24)
SARIMA(2,0,1)(0,0,1,24)
SARIMA(2,0,1)(1,0,1,24)
SARIMA(2,0,2)(1,0,1,24)
SARIMA(1,0,2)(1,0,1,24)
SARIMA(2,0,1)(2,0,1,24)
```

---

## Model Diagnostics

Diagnostic checks performed:

- Residual Plot
- Histogram with Density Estimate
- Q-Q Plot
- Residual ACF
- Ljung-Box Test
- Forecast Confidence Intervals

---

## Key Findings

- Hourly electricity consumption exhibits strong daily seasonality.
- Significant seasonal autocorrelation exists at multiples of 24 hours.
- ARIMA successfully models non-seasonal dependencies.
- SARIMA improves forecasting by incorporating daily seasonal patterns.
- Seasonal decomposition confirms recurring daily consumption behavior.

---

## Tools and Libraries

### Programming Language

- Python

### Libraries

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- Scikit-learn

---

## Repository Structure

```text
├── data/
├── notebooks/
│   └── Electricity_Consumption_Forecasting.ipynb
├── images/
│   ├── distribution_plot.png
│   ├── acf_plot.png
│   ├── pacf_plot.png
│   ├── decomposition_plot.png
│   ├── arima_forecast.png
│   ├── sarima_forecast.png
│   └── diagnostics.png
├── README.md
└── requirements.txt
```

---

## Future Work

The project will be extended by incorporating:

### Machine Learning Models

- Random Forest
- XGBoost
- LightGBM

### Deep Learning Models

- RNN
- LSTM
- GRU
- CNN-LSTM

Model performance will be compared against ARIMA and SARIMA using common forecasting metrics.

---

## Author

**VijayPal Yadav**

M.Sc. Statistics  
Department of Statistics  
University of Delhi
