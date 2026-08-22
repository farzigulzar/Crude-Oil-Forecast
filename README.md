# Forecasting Crude Oil Prices Using LMD, ARIMA, and XGBoost

This repository contains a replication and extension study based on a hybrid forecasting framework for West Texas Intermediate (WTI) crude-oil prices. The workflow combines Local Mean Decomposition (LMD), ARIMA models, and XGBoost to model linear and nonlinear patterns in oil-price time series.

## Overview

Crude-oil prices are characterized by non-stationarity, volatility, structural changes, and nonlinear movement. The hybrid framework uses decomposition to separate high-frequency and lower-frequency components before applying statistical and machine-learning forecasting methods.

The main steps are:

1. Decompose the WTI price series into product functions and a residual component using Local Mean Decomposition.
2. Use Average Mutual Information (AMI) and visual inspection to distinguish stochastic and deterministic components.
3. Model linear time-series structure using ARIMA.
4. Model nonlinear residual behavior using XGBoost.
5. Reconstruct component forecasts and evaluate performance using MAE, RMSE, MAPE, MASE, directional statistics, and Diebold-Mariano comparisons.

## Repository structure

```text
crude-oil-forecasting-lmd-arima-xgboost/
├── notebooks/
│   ├── Assignment_According2Theory.ipynb
│   ├── Assignment_According2Charts.ipynb
│   └── Assignment_According2Theory_matched_arima.ipynb
├── data/
│   └── Cleaned_data.xlsx
├── references/
│   └── A_Novel_Hybrid_Approach_to_Forecasting_Crude_Oil_Prices_Using_Local_Mean_Decomposition_ARIMA_and_XGBoost.pdf
├── presentation/
│   └── Forecasting-Crude-Oil-Prices-PPT.pdf
├── outputs/
├── README.md
├── requirements.txt
└── .gitignore
```

## Notebooks

### Theory implementation

`Assignment_According2Theory.ipynb` implements the hybrid approach according to the methodology described in the reference paper.

### Chart-based extension

`Assignment_According2Charts.ipynb` contains an extension using alternative ARIMA parameter choices and comparison plots.

### Matched-ARIMA extension

`Assignment_According2Theory_matched_arima.ipynb` contains an extension that aligns the ARIMA and residual-processing treatment more closely with the implementation setup examined during the replication.

## Data

The analysis uses cleaned WTI crude-oil price data. Place the data file in the `data/` directory and update the input path in a notebook if needed.

The empirical setup uses a 75% training and 25% testing split. The source study focuses on WTI daily prices over the March 2018 to February 2022 period.

## Installation

Create and activate a virtual environment:

```bash
python -m venv .venv
```

```bash
# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS/Linux
source .venv/bin/activate
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open and run one of the notebooks in the `notebooks/` directory.

## Evaluation metrics

The notebooks use the following forecasting metrics:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)
- Mean Absolute Scaled Error (MASE)
- Directional Statistic (DS)
- Diebold-Mariano (DM) test for forecast comparison

## Reference

Nasir, J., et al. *A Novel Hybrid Approach to Forecasting Crude Oil Prices Using Local Mean Decomposition, ARIMA, and XGBoost.*
