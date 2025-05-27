
# Diffusion Index-Based Recession Forecasting

This project implements a framework for forecasting U.S. economic recessions using **diffusion indices** derived from macroeconomic data, combined with **tree-based ensemble machine learning models**. The methodology aligns with the research presented in the paper _“Diffusion Indices for Economic Recession Forecasting using Tree-Based Ensemble Methods”_.

## Project Highlights

- Uses macroeconomic data from the [FRED-MD](https://research.stlouisfed.org/econ/mccracken/fred-databases/) database
- Constructs novel **Category-Based** and **Factor-Based Diffusion Indices (CBDI, FBDI)**
- Compares performance against traditional benchmarks (e.g., yield curve spread, PCA-based factors, full variable set)
- Forecasts recessions using:
  - Logistic Regression (L1, L2)
  - Random Forest
  - XGBoost
  - Histogram Gradient Boosting
- Implements **expanding-window out-of-sample recursive forecasting**
- Evaluates models using **PR AUC, precision, recall, F1-score**, and **confusion matrices**


## Methodology

### Data:
- **Source:** [FRED-MD](https://research.stlouisfed.org/econ/mccracken/fred-databases/)
- **Period:** 1961 to 2024
- **Target:** NBER-based monthly recession indicator (USRECM)

### Predictors:
- Category-Based Diffusion Indices (CBDI)
- Factor-Based Diffusion Indices (FBDI, Recursive FBDI)
- Yield Spread (10-year minus 3-month Treasuries)
- PCA-based factors (k=8)
- Full FRED-MD dataset (121 variables)

### Models:
- Logistic Regression (L1/L2)
- Random Forest
- XGBoost
- Histogram Gradient Boosting (HGBoost)

### Forecasting Horizon:
- 3-month and 6-month ahead predictions

### Evaluation Strategy:
- Recursive expanding-window forecast
- Hyperparameter tuning using `RandomizedSearchCV`
- Evaluation metrics: PR AUC, F1-score, recall, precision, confusion matrix

## 📊 Key Results

- **Tree-based models significantly outperform Logistic Regression**.
- **CBDI + Tree-Based Models** yield PR AUC > 0.90 for 3-month forecasts, outperforming **full FRED-MD dataset**.
- All diffusion indices outperform the **yield spread**, a traditional benchmark.
- On a 6-month horizon, the **full FRED-MD dataset** performs best, but CBDI remains competitive.

##  Insights

- CBDIs, which aggregate macroeconomic sector trends, are powerful yet very interpretable.
- Diffusion indices allow policymakers to trace economic risks to specific sectors.
- Tree-based models paired with CBDIs provide an ideal balance between **performance and interpretability**.

## References

Key references include:

- McCracken & Ng (2016) – FRED-MD dataset
- Estrella & Mishkin (1998) – Yield curve as recession predictor
- Bai & Ng (2002) – Factor models and PCA
- Chen & Guestrin (2016) – XGBoost
- Gu et al. (2020) – Machine learning in economics

## 📬 Contact
For questions or to view the paper, please reach out to rahulsai.billakanti11@gmail.com.
