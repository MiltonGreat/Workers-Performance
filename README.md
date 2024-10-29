# Employee Performance Prediction

### Summary and Recommendations

#### 1. Overview

This project is designed to predict employee productivity based on various factors such as working conditions, incentives, and work-in-progress (WIP). The goal is to build machine learning models that can predict the actual productivity of employees in a production environment using historical data. The dataset is split into training and testing sets, and the models are evaluated using performance metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), and R-Squared (R²).

#### 2. Data

This dataset includes important attributes of the garment manufacturing process and the productivity of the employees which had been collected manually and also been validated by the industry experts.

Source: https://archive.ics.uci.edu/dataset/597/productivity+prediction+of+garment+employees

The Garment Industry is one of the key examples of the industrial globalization of this modern era. It is a highly labour-intensive industry with lots of manual processes. Satisfying the huge global demand for garment products is mostly dependent on the production and delivery performance of the employees in the garment manufacturing companies. So, it is highly desirable among the decision makers in the garments industry to track, analyse and predict the productivity performance of the working teams in their factories. This dataset can be used for regression purpose by predicting the productivity range (0-1) or for classification purpose by transforming the productivity range (0-1) into different classes.

#### 3. Data Analysis Steps

Data Cleaning:

- Missing Value Imputation: For the wip column, missing values are imputed using the median value.
- Feature Scaling: Continuous variables like over_time, incentive, idle_time, etc., are scaled using StandardScaler for consistent magnitude.

Feature Engineering:

- New features are created to enhance the model's predictive power.
- The test set also has the work_condition_index feature but excludes cumulative_productivity and rolling_productivity_mean as they are dependent on the target.

Modeling:

- The dataset is split into training (80%) and validation (20%) sets.
- Three machine learning models are trained and evaluated: Linear Regression, Random Forest Regressor, Gradient Boosting Regressor
- Each model is evaluated using metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), and R-squared (R²).

Hyperparameter Tuning:

- Random Forest model is fine-tuned using GridSearchCV to optimize hyperparameters such as the number of estimators, maximum depth, and minimum samples split/leaf.

Model Evaluation:

- The Random Forest model is evaluated on the validation set and later used to predict productivity on the test dataset.
- Key metrics (MAE, MSE, R²) and visualizations (Actual vs. Predicted values, Residual plots) are produced to assess model performance.

Visualization:

- Actual vs. Predicted Plot for the Random Forest model.
- Residual Plot to check for patterns in the errors (residuals).
- Feature Importance Plot to understand which features contributed the most to the predictions.

#### 4. Key Findings
      
- Linear Regression performed the worst with an R² score of 0.33, indicating that the model explains 33% of the variance in the productivity data.
- Random Forest Regressor performed the best with an R² score of 0.50 before hyperparameter tuning, and after tuning, the performance slightly improved.
- Gradient Boosting Regressor performed slightly worse than the Random Forest model, with an R² score of 0.49.
- The final Random Forest model was used to predict employee productivity on the test set, and the predictions for the first few samples were close to the actual values, ranging from 0.71 to 0.87.

#### 5. Next Steps

Model Improvement:

- Explore other algorithms such as XGBoost or Neural Networks to improve model accuracy.
- Consider adding more features or performing feature selection to identify the most important predictors of productivity.
- Fine-tune hyperparameters further using RandomizedSearchCV to explore a larger parameter space more efficiently.

Feature Engineering:

- Additional domain-specific features could be engineered, such as employee-specific metrics, shift information, or external conditions (e.g., weather, holidays) that may influence productivity.

#### 6. Source

https://www.kaggle.com/datasets/taeefnajib/workers-performance-prediction-data
