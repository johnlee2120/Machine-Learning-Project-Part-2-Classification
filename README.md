## Part 2: Classification

**Objective:** 

Predict customer churn using telecommunications data and evaluate multiple classification models to optimize retention strategy

**Dataset:** 

- ~7000 customers, 50+ features
- Mix of categorical (contract type, internet type, etc.) and numerical (monthly charges, data usage, etc.) features
- Target: Churn value (0 = stay, 1 = churn)

**Data Processing:**

- Merged multiple tables into a single customer level dataset
- Standardized join key (Customer ID)
- Removed leakage features (post outcome variables like CLTV)
- One hot encoded categorical variables
- Applied min-max scaling
- Train test split (80/20)

**Modeling:**

- Logistic regression
  - L2 Regularization (Ridge)
  - L1 Regularization (Lasso)
  - Elastic Net
- K Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Tree Based Models
  - Decision Tree
  - Bootstrap Aggregation (Bagging)
  - Random Forest
  - Extra Trees
- Boosting
  - AdaBoost
  - XGBoost
- Ensemble Methods
  - Stacking

**Handling Class Imbalance (Balancing Methods):**
 
- Balancing Methods
  - Synthetic Minority Oversampling Technique (SMOTE)
  - Class Reweighing
  - Random Undersampling

**Model evaluation:**

- Metrics
  - Accuracy 
  - Precision
  - Recall
  - F1 Score
  - AUC (ROC)
- Validation
  - Train vs. Test Score Comparison
  - GridSearchCV for hyperparameter tuning
  - Confusion Matrix Analysis
  - ROC & Precision-Recall Curves

**Results:**

Best Model for Test Accuracy

- Stacking (tuned with GridSearchCV)
  - Models stacked: Support Vector Machine (SVM), K nearest neighbors (KNN), Decision Tree Classifier (dt), Final Estimator = Logistic regression (LR)
- **Accuracy = 0.957**
- Highest test accuracy
- Strong generalization (low overfitting gap = 0.00037)

Best for Recall (business-critical)

- Class reweighting + Logistic Regression
- **Recall = 0.9438**
- Compared to Logistic Regression without class reweighing
  - Significantly improved recall (caught more churners)
  - Slight drop in precision (acceptable tradeoff)

**Key Insights:**

- Satisfaction → strongest predictor (low satisfaction = high churn risk)
- Monthly charges → higher cost increases churn
- Contract type → long-term contracts reduce churn
- Tenure (months) → longer customers are less likely to churn

**Model Interpretability:**

- Permutation Feature Independence
- Partial Dependency Plot (PDP)
- Global Surrogate Models
- Local Interpretable Model-agnostic Explanations (LIME)

## Images:

<p align="center">
  <img src="Images/stacking_table.png" width="800"/>
</p>

<p align="center">
  <em>Predicted vs Actual prices using Lasso Regression (strong linear fit)</em>
</p>

<p align="center">
  <img src="Images/lr_class_reweighing_table.png" width="800"/>
</p>

<p align="center">
  <em>Before and after log transforming the "engine size" feature</em>
</p>


<p align="center">
  <img src="Images/feature_importance_plot.png" width="500"/>
</p>

<p align="center">
  <em>Model comparisons (Lasso is strongest)</em>
</p>

<p align="center">
  <img src="Images/partial_dependency_plot.png" width="500"/>
</p>

<p align="center">
  <em>Model comparisons (Lasso is strongest)</em>
</p>

