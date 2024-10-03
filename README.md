House Price Prediction - TRAZZ PEPPER

This project focuses on predicting house prices using a dataset from Kaggle. The goal is to explore and understand the relationships between different feature variables and the final sale price of houses. I've extensively commented on the code to explain what I’m doing at each step and why.

Dataset

The dataset used for this project is from Kaggle, containing detailed information about house sales. The dataset includes variables related to various aspects such as location, type of house, construction quality, and more. The data is stored in a CSV file (train.csv).

Project Workflow

1. Data Preparation
    * Loaded the data into a Pandas DataFrame and explored the features.
    * Applied extensive data cleaning and feature engineering to improve model performance:
    * Converted categorical variables into dummy/indicator variables.
    * Filled missing values using the median.
    * Created new feature variables from existing data (e.g., interaction terms, squaring variables, etc.).

2. Feature Engineering
    * A significant part of the project was engineering new features to enhance the predictive power:
    * Binarized OverallQual and OverallCond (quality and condition variables) into multiple boolean features.
    * Created new interaction features like TotalBsmtSF_squared_FE, GarageArea_to_TotalArea_FE, and more.

3. Model Building
I experimented with different models to predict house prices:

Linear Regression: A basic linear model was trained as a starting point. The model showed a good fit on the training data   but performed poorly on the test data due to overfitting or high variance.
Random Forest Regressor: A more robust model, which performed much better after tuning using cross-validation and a grid search for hyperparameters.

4. Model Evaluation
The performance of models was evaluated using cross-validation and test data.
Random Forest model's best cross-validation score was 0.8467, and the test score (R²) was 0.8723.

5. Next Steps
Too many variables? I noticed that increasing the number of features improves accuracy, but it raises concerns about potential multicollinearity. I plan to reduce the number of variables without affecting model performance.
Handling missing data: Currently, missing values are filled with the median. I aim to explore better imputation techniques in future iterations.

6. Packages Used
Pandas for data manipulation.
NumPy for numerical operations.
Matplotlib and Seaborn for visualizations.
Scikit-learn for model building and evaluation.

8. Results
The model's has a value of 0.149 at its best on kaggle.
