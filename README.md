README: House Price Prediction Project
By TRAZZ PEPPER
Score: 0.129 on Kaggle (top 800 as of 10/2024)

Project Overview

This project aims to predict house prices using various machine learning models, including Linear Regression, Random Forest, LightGBM, CatBoost, and XGBoost. It involves data conditioning, feature engineering, and hyperparameter tuning with Optuna. The dataset consists of housing data with features such as overall quality, condition, and other structural attributes.


1. Data Conditioning Function
The data_conditioning() function preprocesses the dataset to prepare it for model training and testing.


Categorical Encoding: Converts categorical columns into dummy variables using pd.get_dummies().

Feature Engineering:
Creates boolean variables for OverallQual, OverallCond, and MSSubClass to reflect their categorical nature.

New features derived from existing ones:
Squared values of TotalBsmtSF and LotFrontage.
Interaction terms between TotalBsmtSF and GarageArea.
Age of the house, total number of baths, rooms, etc.

Missing Data Handling: Fills missing values with the median of each column.
Data Cleansing: Removes unnecessary columns and replaces spaces in column names with underscores.

2. Correlation Analysis and Feature Selection
Correlation Matrix: A correlation matrix is computed to find features with strong correlations with the target variable SalePrice.
Feature Selection: Only features with a correlation above 0.05 are kept for further analysis.

3. Modeling
Multiple models are used for predicting house prices. Data is split into training and testing sets, and standard scaling is applied to the features.

3.1 Linear Regression
A basic linear regression model is used to establish a baseline performance. The model is evaluated using R² and Mean Squared Log Error (MSLE).

3.2 Random Forest Regressor (with Optuna Tuning)
Hyperparameter Tuning: Optuna is used to find the best hyperparameters for the RandomForestRegressor.
Objective: Minimize MSLE using cross-validation and model performance on the test set.

3.3 LightGBM Regressor (with Optuna Tuning)
Hyperparameter Tuning: Optuna is used to optimize LightGBM model parameters, including the number of leaves, regularization terms, and learning rate.
Objective: Minimize MSLE using the LightGBM model.

3.4 CatBoost Regressor (with Optuna Tuning)
Hyperparameter Tuning: Optuna tunes the hyperparameters for the CatBoost model.
Objective: Minimize MSLE and evaluate the best CatBoost model's performance.

3.5 XGBoost Regressor (with Optuna Tuning)
Hyperparameter Tuning: XGBoost model parameters are optimized using Optuna.
Objective: Minimize MSLE and evaluate the performance of the XGBoost model.

4. Optuna for Hyperparameter Optimization
Each model's hyperparameters are optimized using Optuna, a framework for automatic hyperparameter optimization. It maximizes model performance by minimizing the negative MSLE metric over multiple trials.

Parameters Tuning: Includes parameters such as the number of estimators, max depth, learning rate, etc.
Number of Trials: Models are optimized for a set number of trials (e.g., 150-400 trials depending on the model).

5. Model Evaluation
After training, the best models are evaluated on the test dataset.
Metrics used for evaluation:
R² Score: Measures the proportion of variance explained by the model.
MSLE: The square root of the mean squared logarithmic error between predicted and actual house prices.

6. Files and Output
The correlation matrix and highly correlated variables are stored for feature selection.
The results of the models, including their R² scores and MSLE, are printed to the console.
Best Hyperparameters for each model are also printed after Optuna tuning.

Conclusion

This project explores different machine learning models and techniques to predict house prices. By utilizing feature engineering and hyperparameter tuning, the models' performance is optimized for better accuracy in predictions.