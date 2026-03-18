## Project Status

**Completed:** End to end regression pipeline (EDA, preprocessing, feature engineering, evaluation, regularization)

**In Progress:** Expanding to classification models (logistic regression, tree based methods, etc.)


## Phase 1: Regression Modeling

**Objective:** 

Predict car prices using structured automotive data and evaluate multiple regression approaches

**Dataset:** 

- ~200+ observations, 25 features
- Mix of categorical and numerical features
- Target: Price

**Data Processing:**

- Handled categorical variables via one-hot encoding
- Feature engineering (i.e. creating brand_category based on average prices)
- Log transformation applied to reduce skew 
- Train test split (70/30)

**Modeling:**

- Linear regression
- Polynomial regression (degree tuning)
- Regularization:
  - Ridge
  - Lasso
  - Elastic Net
- SGD-based regression

**Model evaluation:**

- Metrics
  - RMSE
  - R² Score
- Cross validation (3-fold, 5-fold)
- Residual analysis + diagnostic plots

**Results:**

- Best Model - Lasso Regression
- R²: 0.80 (highest)
- RMSE: 3711.17 (lowest)
- Regularization improved generalization vs polynomial overfitting

**Key Insights:**

- Engine size and curb weight are strong predictors
- Polynomial features caused severe overfitting without regularization
- Scaling is critical for SGD performance

**Images:**

<p align="center">
  <img src="Images/predicted%20vs%20actual.png" width="450"/>
</p>

<p align="center">
  <em>Predicted vs Actual prices using Lasso Regression (strong linear fit)</em>
</p>

<p align="center">
  <img src="Images/before%20and%20after%20log.png" width="600"/>
</p>

<p align="center">
  <em>Before and after log transforming the "engine size" feature</em>
</p>


<p align="center">
  <img src="Images/model%20comparisons.png" width="300"/>
</p>

<p align="center">
  <em>Model comparisons (Lasso is strongest)</em>
</p>



