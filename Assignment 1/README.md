# Assignment 1 — Airbnb Pricing Model

**Course:** ECBS5171 — Data Analysis 3  
**Author:** Boga Petruska  
**Date:** February 2, 2026

## Overview

Predictive pricing models for Airbnb listings. Trained on San Diego Q4 2024, validated on San Diego Q3 2025 (temporal) and Broward County Q3 2025 (geographic).

## Results

| Model | Train RMSE | Temporal RMSE | Geo RMSE |
|-------|-----------|---------------|----------|
| Gradient Boosting | $150.42 | $152.87 | $145.13 |
| Random Forest | $156.32 | $146.73 | $147.19 |
| XGBoost | $158.54 | $154.91 | $161.42 |
| OLS | $171.43 | $160.05 | $21,585 |
| LASSO | $171.48 | $159.87 | $22,852 |

Key finding: tree-based models generalize across cities; linear models fail catastrophically on new geographies due to location-specific coefficients.

## File Structure

```
Assignment 1/
├── analysis/
│   └── Petruska_Boglarka_Assignment_1 - v2.ipynb
├── data/
│   ├── San Diego 2024 Q4 listings.csv
│   ├── San Diego 2025 Q3 listings.csv
│   └── Broward County 2025 Q3 listings.csv
├── outputs/
│   ├── feature_importance.png
│   ├── shap_cart.png
│   └── shap_cart_summary.png
├── requirements.txt
├── README.md
└── LICENSE
```

## Data

Source: [Inside Airbnb](http://insideairbnb.com/get-the-data/)

- **Training:** San Diego, Q4 2024 (12,844 raw → 11,543 after cleaning)
- **Temporal validation:** San Diego, Q3 2025 (11,223 after cleaning)
- **Geographic validation:** Broward County FL, Q3 2025 (11,605 after cleaning)

## Setup

```bash
pip install -r requirements.txt
```

Open and run `analysis/Petruska_Boglarka_Assignment_1 - v2.ipynb` from top to bottom.
