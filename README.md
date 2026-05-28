# Kalimati Price Prediction — Machine Learning

Predicting vegetable prices from Kathmandu's Kalimati market using Linear Regression and Random Forest Regressor.
Built on 96,480 daily price records across 133 commodities (January 2021 – September 2023).

## Results

| Model | MAE | RMSE | R² |
|-------|-----|------|----|
| Linear Regression | NPR 2.13 | NPR 5.54 | 99.8% |
| **Random Forest** | **NPR 0.80** | **NPR 2.78** | **99.9%** |

Random Forest outperforms Linear Regression on all metrics.

## Key Findings

- **Min_Price is the strongest predictor** (91% feature importance) — the daily price spread drives the average
- **Time-based split used** to prevent data leakage — model trained on 2021-2022, tested on 2023
- **Per-commodity encoding** — 133 commodity types label encoded for ML compatibility

## Project Structure

```
kalimati-ml-price-prediction/
├── price_prediction_v2.py    # Main ML script
├── README.md
```

## Tech Stack

- **Python** — core language
- **Pandas** — data loading and feature engineering
- **Scikit-learn** — LinearRegression, RandomForestRegressor, LabelEncoder
- **Matplotlib** — visualization

## Features Engineered

| Feature | Description |
|---------|-------------|
| Commodity_Encoded | Label encoded commodity name |
| Year, Month, Day | Extracted from Date column |
| DayOfWeek | 0=Monday, 6=Sunday |
| DayOfYear | 1–365 |
| Quarter | 1–4 |
| Season | 0=Winter, 1=Spring, 2=Summer, 3=Autumn |
| Min_Price | Daily minimum price |
| Max_Price | Daily maximum price |

## Run Locally

```bash
pip install pandas scikit-learn matplotlib
python price_prediction_v2.py
```

Update `DATA_PATH` in the script to point to your Kalimati CSV file.

## Data

Dataset: Kalimati Tarkari Bazar daily price records
Columns: `Commodity, Date, Unit, Min_Price, Max_Price, Average_Price`
Source: Kalimati Fruits and Vegetable Market Development Board

## Sample Prediction

```
Commodity : Tomato Big(Nepali)
Date      : June 01, 2023
Linear Regression : NPR 66.64
Random Forest     : NPR 65.49
```

## Concepts Applied

- Supervised learning — regression
- Feature engineering from datetime
- Label encoding for categorical variables
- Time-based train/test split (no data leakage)
- Model evaluation: MAE, RMSE, R²
- Feature importance analysis

## Developer

Sushmita Shrestha — [github.com/sshrestha000](https://github.com/sshrestha000)
