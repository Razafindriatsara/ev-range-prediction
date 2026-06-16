# ⚡ EV Battery Range Prediction

> Predicting remaining driving range of electric vehicles using supervised machine learning — directly relevant to BMW iX / i4 / i5 electromobility.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)

---

## 📋 Project Overview

**Range anxiety** is the #1 barrier to EV adoption. This project builds a machine learning model that predicts a vehicle's remaining driving range in real time, based on battery state, driving behaviour, environmental conditions, and vehicle load.

**Business question:** Can we predict remaining EV range more accurately than simple battery-percentage estimates?

---

## 🎯 Results

| Model | RMSE (km) | MAE (km) | R² |
|---|---|---|---|
| Linear Regression | ~12 | ~9 | ~0.97 |
| Random Forest | ~8 | ~6 | ~0.99 |
| Gradient Boosting | ~9 | ~7 | ~0.98 |

**Best model: Random Forest** — lowest error, highest explanatory power.

---

## 🔍 Key Findings

- **Battery SoC** is the strongest predictor, but alone is insufficient
- **Ambient temperature** causes up to 40 km range loss in winter conditions
- **Driving style** (acceleration aggressiveness) affects range by up to 80 km
- **HVAC load** (heating/cooling) is a significant hidden factor

---

## 🛠️ Tech Stack

- **Python** — pandas, numpy, matplotlib, seaborn
- **Machine Learning** — scikit-learn (LinearRegression, RandomForestRegressor, GradientBoostingRegressor)
- **Evaluation** — RMSE, MAE, R², feature importance

---

## 📁 Features Used

| Feature | Description |
|---|---|
| `battery_soc_%` | State of charge (%) |
| `avg_speed_kmh` | Average driving speed |
| `ambient_temp_c` | Outside temperature |
| `battery_temp_c` | Battery pack temperature |
| `acceleration_score` | Driving aggressiveness (0–1) |
| `hvac_load_kw` | Climate control power draw |
| `payload_kg` | Passengers + luggage weight |
| `road_gradient_%` | Road slope (positive = uphill) |
| `tire_pressure_loss` | Normalized pressure deficit |

---

## 🚀 Getting Started

```bash
git clone https://github.com/Razafindriatsara/ev-range-prediction
cd ev-range-prediction
pip install pandas numpy scikit-learn matplotlib seaborn
jupyter notebook ev_range_prediction.ipynb
```

---

## 🏎️ BMW Relevance

This model is a foundation for:
- Real-time range display in BMW's iDrive software stack
- Predictive range warnings based on route + weather data
- Personalized range estimation per driver profile
- Integration with BMW Connected Drive navigation
