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

## 📊 Dataset Information

* **Source Target**: Total Energy Electric Power Sector $\text{CO}_2$ Emissions (`Description == "Total Energy Electric Power Sector CO2 Emissions"`)
* **Unit of Measurement**: Million Metric Tons of Carbon Dioxide ($\text{MMT CO}_2$)
* **Time Granularity**: Monthly (`YYYYMM` format transformed to datetime `ds`)

### Sample Data Format
| Date (`YYYYMM` / `ds`) | Value (`y`) | Description | Unit |
| :--- | :--- | :--- | :--- |
| `1973-01-01` | `72.076` | Total Energy Electric Power Sector CO2 Emissions | Million Metric Tons |
| `1973-02-01` | `64.442` | Total Energy Electric Power Sector CO2 Emissions | Million Metric Tons |

---

## 🔬 Methodology & Modeling Approaches

```mermaid
flowchart TD
    A[Raw Data: data.csv] --> B[Filter Electric Power Sector & Format Datetime]
    B --> C[Clean & Handle Missing Values]
    C --> D1[Prophet Modeling Pipeline]
    C --> D2[XGBoost Feature Engineering]

    D1 --> E1[Multiplicative Seasonality Setup]
    E1 --> F1[2-Year Train/Test Holdout Evaluation]
    F1 --> G1[Full Dataset Training & 120-Month Extrapolation]