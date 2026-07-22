# House Price Prediction

A machine learning project that predicts house prices in King County, Washington using Linear Regression and Random Forest Regressor.

---

## Dataset

**KC House Data** — 21,613 house sales in King County, Washington (May 2014 to May 2015)

You can load the dataset in one of two ways:

**Option 1: Use the CSV file directly**
```python
import pandas as pd

housing_data = pd.read_csv('kc_final.csv')
```

**Option 2: Download from Kaggle**
```python
import kagglehub

path = kagglehub.dataset_download("astronautelvis/kc-house-data")
print("Path to dataset files:", path)
```

---

## Features Used

| Feature | Description |
|---|---|
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `sqft_living` | Square footage of the living space |
| `sqft_lot` | Square footage of the lot |
| `floors` | Number of floors |
| `waterfront` | Whether the house has a waterfront view |
| `view` | Number of times the house has been viewed |
| `condition` | Overall condition of the house |
| `grade` | Overall grade given to the housing unit |
| `sqft_above` | Square footage of the house apart from the basement |
| `sqft_basement` | Square footage of the basement |
| `yr_built` | Year the house was built |
| `yr_renovated` | Year the house was renovated |
| `zipcode` | ZIP code of the house location |
| `lat` | Latitude coordinate |
| `long` | Longitude coordinate |
| `sqft_living15` | Living area square footage in 2015 |
| `sqft_lot15` | Lot square footage in 2015 |

**Target:** `price` — the sale price of the house

---

## Models

### Linear Regression
A baseline model using scikit-learn's `LinearRegression`. The dataset is split 80/20 for training and testing with `random_state=42`.

### Random Forest Regressor
An ensemble model using 100 estimators (`n_estimators=100`, `random_state=42`), which significantly outperforms the linear baseline.

---

## Evaluation Metrics

Both models are evaluated using:

| Metric | Description |
|---|---|
| MAE | Mean Absolute Error — average dollar difference between predicted and actual price |
| RMSE | Root Mean Squared Error — penalises larger errors more heavily |
| R² Score | Proportion of variance in price explained by the model |

---

## Example Prediction

The notebook includes a sample prediction for a house with the following attributes:

| Attribute | Value |
|---|---|
| Bedrooms | 3 |
| Bathrooms | 2 |
| Living Area | 2,000 sqft |
| Lot Size | 5,000 sqft |
| Floors | 1 |
| Waterfront | No |
| Condition | 3 |
| Grade | 7 |
| Year Built | 1995 |
| ZIP Code | 98103 |
| Latitude / Longitude | 47.656 / 122.34 |

---

## Requirements

```
pandas
scikit-learn
kagglehub
```

Install all dependencies with:

```bash
pip install pandas scikit-learn kagglehub
```

---

## Usage

1. Clone this repository
2. Either place `kc_final.csv` in the project folder or download it via `kagglehub`
3. Open `House_Price_Prediction.ipynb` in Jupyter
4. Run all cells in order
