# Comparative Analysis of SARIMAX and NNARX in Forecasting Inflation Using Temperature as an Exogenous Variable
## Overview
Inflation is one of the most critical economic indicators, influencing everything from daily household expenses to national fiscal policy. Forecasting it accurately is essential for:

- Governments (for policy planning)

- Businesses (for pricing and budgeting)

- Households (for financial decision-making)

However, traditional forecasting methods like ARIMA often rely solely on past inflation data. What if we also consider external factors, like climate change?

This project explores how temperature might affect inflation by using it as an exogenous variable in forecasting models.

i aim to carry out a comparative analysis of the predictive performance of a traditional statistical model ,SARIMAX, and a neural network model ,NNARX.

The objective is to evaluate and compare the performance of SARIMAX and NNARX models in forecasting inflation (CPI) using temperature as an exogenous input.

I also aim to answer the following questions:

- Does temperature influence inflation?

- Which model captures this relationship better?


---

## Methodology

Here’s a step-by-step explanation of the workflow I used:

### 1. Data Collection & Preprocessing
- Imported a dataset containing monthly records of inflation (CPI) and temperature.
- Renamed columns and handled missing values (filled temperature using mean imputation).
- Converted the 'Year' column into a datetime object and set it as the index.
- Plotted the inflation and temperature trends over time for initial exploration.

### 2. Exploratory Data Analysis (EDA)
- Visualized trends and seasonality in CPI and temperature.
- Conducted stationarity tests using Augmented Dickey-Fuller test.
- Applied differencing to remove trends and seasonality.

### 3. Modeling

#### A. SARIMAX
- Identified order (p,d,q)(P,D,Q) using ACF and PACF plots.
- Fitted the SARIMAX model with temperature as an exogenous variable using pmdarima's auto_arima.
- Used the best model from auto_arima to fit SARIMAX model using statsmodel.  
- Forecated using the model.
- Carried out hyperparameter tuning to obtain the best parameter.
- fitted SARIMAX using best parameters from tuning.

#### B. NNARX
- Framed the time series prediction as a supervised learning task.
- Created lagged inflation and temperature features.
- Designed a neural network using Keras with input, hidden, and output layers.
- Trained the model and generated forecasts.
- Carried out hyperparameter tuning randomly in ten trials.
- Fitte NNARX using the best parameters .
- Carried out forecasting using the re-trained model.

### 4. Model Evaluation

The performance of both models was evaluated using three metrics:

| Metric | Description |
|--------|-------------|
| RMSE   | Penalizes larger errors more heavily |
| MAE    | Gives equal weight to all errors |
| MAPE   | Useful for percentage error interpretation |

---

## Results

- NNARX outperformed SARIMAX across all three evaluation metrics.
- The neural network model better captured the non-linear patterns influenced by temperature.
- Shows the potential of deep learning methods in macroeconomic forecasting.

---

## Dependencies

To run this project, install the following libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn tensorflow statsmodel pmdarima keras itertools
```

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/taylorwanyama/Comprative-Analysis-between-SARIMAX-and-NNARX-Model-in-Forecasting-Inflation-using-Temperature./edit/main/README.md

## Author
[Taylor Wanyama] 
