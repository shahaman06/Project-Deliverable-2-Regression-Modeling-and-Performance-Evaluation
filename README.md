# Project Deliverable 2

## Project Overview
This deliverable continues from Deliverable 1, focusing on predictive modeling using the cleaned Wine Quality dataset.  
The objective is to develop regression models to predict wine quality, evaluate their performance, and derive insights for data-driven decisions.

---

## Dataset Summary
- **Dataset Name:** Wine Quality (Red Wine)  
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)  
- **Instances:** 1,598 (after cleaning)  
- **Attributes:** 11 physicochemical features + quality score  
- **Cleaned Dataset:** Duplicates removed, outliers filtered using Z-score, saved as `winequality-red-cleaned.csv`.

**Purpose:**  
- Predict wine quality using physicochemical attributes.  
- Explore regression techniques and assess model performance.  

---

## Feature Engineering
- **Interaction Feature:** `alcohol * citric acid` to capture joint effects.  
- **Ratio Feature:** `free sulfur dioxide / total sulfur dioxide` to represent relative sulfur content.  
- **Polynomial Feature:** `volatile acidity²` to model non-linear relationships.  

**Rationale:** Engineered features aim to improve predictive accuracy by capturing non-linearities and feature interactions.

---

## Regression Models Implemented
1. **Linear Regression**  
   - Baseline model capturing linear relationships.  

2. **Ridge Regression**  
   - Regularized model to reduce multicollinearity effects.  

3. **Lasso Regression**  
   - Regularized model that can shrink less important coefficients toward zero.  

---

## Model Evaluation Metrics

| Model   | MSE    | RMSE   | R²    | Mean CV R² |
|---------|--------|--------|-------|------------|
| Linear  | 0.42   | 0.65   | 0.35  | 0.35       |
| Ridge   | 0.41   | 0.64   | 0.37  | 0.36       |
| Lasso   | 0.43   | 0.66   | 0.34  | 0.34       |

**Interpretation:**  
- Ridge regression slightly outperforms other models in both R² and RMSE.  
- Cross-validation confirms Ridge generalizes well on unseen data.  
- Feature engineering contributes to improved model accuracy.

---

## Visualizations
1. **Actual vs Predicted Wine Quality (Ridge Regression)**  
   - Shows that predicted values align well with actual values, though some overlap exists.  

2. **RMSE Comparison Across Models**  
   - Ridge regression shows the lowest RMSE among the three models.  

These visualizations demonstrate model performance and provide insights for future improvements.

---

## Key Observations
- Engineered features improved predictive performance.  
- Alcohol and volatile acidity consistently emerge as strong predictors of wine quality.  
- Ridge regression is the best-performing model due to its regularization handling multicollinearity.  
- RMSE values (~0.64–0.66) indicate moderate predictive accuracy.  
- Linear and Lasso regression are useful baselines but slightly less robust.  
- Cross-validation confirms that models generalize well to unseen data.

---

## Challenges Encountered
- Handling skewed distributions and feature scaling.  
- Determining which features and interactions would improve predictive performance.  
- Balancing model complexity and generalization to avoid overfitting.  

---

## Next Steps
- Explore additional feature engineering (e.g., polynomial features for other variables).  
- Consider advanced models (Random Forest, Gradient Boosting).  
- Potentially convert wine quality into categorical classes for classification modeling.  
- Hyperparameter tuning for Ridge and Lasso regression to optimize performance.
