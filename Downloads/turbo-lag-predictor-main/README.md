# Turbo Lag Prediction using Machine Learning

## Overview

This project simulates engine telemetry data and predicts turbo lag (in milliseconds) using a Gradient Boosting Regressor (GBT). It combines time-series feature engineering, data-driven lag detection, and a real-time dashboard for inference.

---

## Features

- Synthetic engine telemetry generation
- Data preprocessing and noise handling
- Feature engineering (rolling statistics, derivatives, interactions)
- Turbo lag label generation using signal-based detection
- Gradient Boosting model for regression
- Performance evaluation with MAE, RMSE, and R²
- Diagnostic visualizations (prediction vs actual, residual analysis)
- Real-time prediction dashboard using Tkinter

---

## Project Structure

```
turbo-lag-predictor/
│
├── generate_data.py
├── main_ml.py
├── ui_dashboard.py
│
├── engine_telemetry.csv
├── turbo_lag_gbt_model.pkl
├── turbo_lag_scaler.pkl
├── turbo_lag_diagnostics.png
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Installation

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

### 1. Generate dataset

```bash
python generate_data.py
```

### 2. Train model

```bash
python main_ml.py
```

### 3. Run dashboard

```bash
python ui_dashboard.py
```

---

## Model Pipeline

1. Load and validate telemetry data
2. Handle missing values using forward/backward fill
3. Smooth signals using rolling averages
4. Generate derived features:
   - First-order differences (dRPM, dThrottle, dBoost)
   - Rolling mean and standard deviation
   - Engine load and interaction features

5. Detect turbo lag events using threshold-based signal analysis
6. Construct time sequences
7. Extract statistical features from sequences
8. Train Gradient Boosting Regressor
9. Evaluate using regression metrics

---

## Evaluation Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Current performance (approximate):

- R² ≈ 0.39

---

## Outputs

- Predicted vs actual turbo lag plot
- Residual distribution histogram
- Residual trends over time

---

## Notes

- Model artifacts (`.pkl`) can be excluded from version control and regenerated
- Dataset can be regenerated using the data generation script
- Performance depends on realism of simulated data

---

## Possible Improvements

- Replace GBT with sequence models (LSTM, GRU)
- Improve lag labeling using domain-specific rules
- Introduce real-world telemetry data
- Deploy dashboard as a web application (e.g., Streamlit)

---

## Author

Sachin K
