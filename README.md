# Workers-Performance

### Summary and Recommendations

#### 1. Overview

This project is designed to predict employee productivity based on various factors such as working conditions, incentives, and work-in-progress (WIP). The goal is to build machine learning models that can predict the actual productivity of employees in a production environment using historical data. The dataset is split into training and testing sets, and the models are evaluated using performance metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), and R-Squared (R²).

#### 2. Data

This dataset includes important attributes of the garment manufacturing process and the productivity of the employees which had been collected manually and also been validated by the industry experts.

Source: https://archive.ics.uci.edu/dataset/597/productivity+prediction+of+garment+employees

The Garment Industry is one of the key examples of the industrial globalization of this modern era. It is a highly labour-intensive industry with lots of manual processes. Satisfying the huge global demand for garment products is mostly dependent on the production and delivery performance of the employees in the garment manufacturing companies. So, it is highly desirable among the decision makers in the garments industry to track, analyse and predict the productivity performance of the working teams in their factories. This dataset can be used for regression purpose by predicting the productivity range (0-1) or for classification purpose by transforming the productivity range (0-1) into different classes.

#### 3. Data Analysis Steps

Data Loading and Preprocessing:

- The training and testing datasets are extracted from a ZIP file.
- Duplicated columns are removed to avoid redundancy.
- Missing values in the wip column are imputed using the median value to fill gaps in the data.
- Feature scaling is applied to continuous variables (over_time, incentive, idle_time, etc.) to standardize them using StandardScaler.

Feature Engineering:

- A Work Condition Index is created by taking the mean of wip, over_time, and incentive, which provides an aggregate measure of working conditions for each observation.

Splitting Data:

- The training dataset is split into training and validation sets, where 80% is used for training models, and 20% is used for validation.

Model Training and Evaluation

Making Predictions:

- The best-performing model (Random Forest) is used to make predictions on the test set. The output includes the predicted employee productivity for the test set based on the features provided.

#### 4. Key Findings
      
Model Performance:

- Although the R² score of 0.3095 shows that the model explains about 31% of the variance in productivity, there is room for improvement. This suggests that other factors not present in the dataset may be influencing productivity, or the feature engineering could be enhanced further.

Predictions on Test Data:

- The test set predictions show productivity estimates ranging from approximately 0.6717 to 0.8727. These predictions can be used to understand how employees are expected to perform under certain conditions.

Feature Importance and Work Conditions:

- The Work Condition Index is a useful aggregate feature that can help summarize the effect of multiple factors on employee productivity. 

Missing Values Handling:

- The project uses a straightforward approach to handling missing values by imputing the median for numeric columns (like wip). This method ensures that no data is lost, but it could be further improved by using more advanced imputation techniques or incorporating domain knowledge to better estimate missing values.

#### 5. Next Steps

Model Improvement:

- Explore other algorithms such as XGBoost or Neural Networks to improve model accuracy.
- Consider adding more features or performing feature selection to identify the most important predictors of productivity.
- Fine-tune hyperparameters further using RandomizedSearchCV to explore a larger parameter space more efficiently.

Feature Engineering:

- Additional domain-specific features could be engineered, such as employee-specific metrics, shift information, or external conditions (e.g., weather, holidays) that may influence productivity.

#### 6. Source

https://www.kaggle.com/datasets/taeefnajib/workers-performance-prediction-data
