# CIE-2 Activity 1: Multiple Linear Regression (House Price Prediction)

**Student roll number:** AD3125
**Course:** Regression and Classification Algorithms (RCA), T.Y. B.Tech AI & Data Science, Zeal College of Engineering and Research
**Submission GitHub ID:** https://github.com/complexiota

## Dataset
- **Source:** Yasser H., *Housing Prices Dataset*, Kaggle. https://www.kaggle.com/datasets/yasserh/housing-prices-dataset/data
- **File:** `Housing.csv`, 545 rows, 13 columns (1 target, 12 input features). Currency is not stated in the source.
- **Target (y):** `price`
- **Inputs (X):** area, bedrooms, bathrooms, stories, parking, mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea, furnishingstatus

## What is in this repo
- `AD3125_Activity1_Multiple_Linear_Regression.ipynb`: the executed notebook. It covers EDA, correlation analysis, a manual normal-equation calculation on 8 houses (verified with scikit-learn), an 80:20 train/test split, a mean baseline, a single-feature model (area), a multiple regression model, test-set metrics, VIF, residual analysis, a new prediction, and a decision log.

## Key results (test set, 109 houses)

| Metric | Mean baseline | Single feature (area) | Multiple regression |
|---|---|---|---|
| MAE | 1,748,625 | 1,474,748 | 970,043 |
| RMSE | 2,268,298 | 1,917,104 | 1,324,507 |
| R² | -0.018 | 0.273 | 0.653 |
| Adjusted R² | -0.018 | 0.266 | 0.605 |

- Bathrooms, area, and air conditioning have the largest standardised effects on price.
- All VIF values are below 2, so multicollinearity is not a concern.
- Residuals are right-skewed and their spread grows with predicted price, so the model is least reliable for expensive houses.

## Limitations
- Linear model: it misses the curved relationship at the top of the market.
- No location information, which is likely the largest missing driver of price.
- Associations only, not causation. Predictions are estimates, not valuations.

## How to run
1. Place `Housing.csv` in the same folder as the notebook.
2. Install: `pandas numpy matplotlib seaborn scikit-learn statsmodels`.
3. Open the notebook and run all cells from top to bottom. A fixed random seed (42) makes results reproducible.

   **Submission GitHub ID:** [github.com/complexiota](https://github.com/complexiota)
   
