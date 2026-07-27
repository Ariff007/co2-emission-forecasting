# 🌿 CO2 Emission Forecasting (10-Year Horizon)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Prophet](https://img.shields.io/badge/Model-Facebook%20Prophet-orange.svg)](https://facebook.github.io/prophet/)
[![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)](https://xgboost.readthedocs.io/)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](#license)

---

## 📌 Project Overview

Energy consumption and power generation are primary contributors to greenhouse gas emissions. Analyzing historical monthly emissions trends and producing reliable 10-year forecasts provides critical insights for policymakers, environmental scientists, and energy analysts.

This project delivers:
1. **Data Preprocessing & Cleaning**: Extraction and formatting of historical monthly $\text{CO}_2$ emissions (Million Metric Tons).
2. **Feature Engineering**: Autoregressive lag creation ($\text{lag}_1, \text{lag}_{12}$) and temporal attributes (month/seasonality).
3. **Model Training & Evaluation**:
   - **Facebook Prophet**: Multiplicative seasonality model evaluated on a 2-year (24-month) holdout test set using **MAPE**, **MAE**, and **RMSE**.
   - **XGBoost Regressor**: Iterative recursive step-by-step 10-year forecasting model with dynamic feature recalculation.
4. **Notebook Generators**: Python automation scripts (`create_nb.py`, `create_prophet_nb.py`) that programmatically instantiate clean, ready-to-run Jupyter Notebooks.
5. **Report Exports**: PDF summary outputs for quick evaluation and visual distribution.

---