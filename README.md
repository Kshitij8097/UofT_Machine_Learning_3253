Crime‑Risk Prediction Model for Insurance Premium Pricing
A machine‑learning project that predicts high‑risk vs low‑risk geographic grids using spatial, temporal, and contextual crime data. Designed to support insurers in setting fair, risk‑aligned premiums.

Author
Kshitij

Project Overview
This project builds a crime‑risk prediction model using:

Spatial features (latitude, longitude)

Temporal features (year, month, day, hour, day‑of‑week)

Contextual features (premises type, location type)

The model outputs whether a grid is high‑risk or low‑risk, enabling insurers to adjust premiums based on objective risk patterns.

Dataset
The dataset includes:

Crime incident records

Geographic coordinates

Time of occurrence

Premises and location types

Engineered target variable: IS_HIGH_RISK_GRID

All categorical features were one‑hot encoded into df_encoded.

Feature Engineering
Key engineered features:

Spatial: LAT, LONG

Temporal: OCC_YEAR, OCC_MONTH, OCC_DAY, OCC_HOUR, OCC_DOW

Contextual: One‑hot encoded premises and location types

Models
Logistic Regression (Baseline)
Linear model

Failed to capture spatial complexity

Predicted all points as high‑risk

Random Forest Classifier (Primary Model)
Captured non‑linear spatial patterns

Strong predictive performance

Meaningful feature importance

Used for final predictions

Visualizations
The project includes:

Actual crime‑risk map

Random Forest predicted risk map

Feature importance plots

Spatial scatterplots

Prediction Functions
Two helper functions are included:

1. Numeric‑only prediction
python
predict_risk_numeric(lat, long, hour, day, month, year)
2. Full prediction with categorical inputs
python
predict_risk_full(lat, long, hour, day, month, year, premises_type, location_type)
Both return:

Predicted class (0 = low risk, 1 = high risk)

Probability of high risk

How Insurers Use This Model
Premium pricing: Adjust premiums based on predicted risk

Underwriting: Flag high‑risk applications

Loss prevention: Identify hotspots and fraud patterns

Portfolio management: Balance geographic exposure

Project Structure
Code
├── data/
├── notebooks/
├── src/
│   ├── preprocessing.py
│   ├── modeling.py
│   ├── visualization.py
│   └── prediction_utils.py
├── README.md
└── requirements.txt
