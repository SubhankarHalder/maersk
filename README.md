# Maersk ML Assignment Challenge

## By Subhankar Halder

In this challenge we are given a time-series dataset and we are asked to come up with ML models to predict the "Sourcing Cost" for various entries of products. We have been given an xlsx file containing the instructions for the task, the training set and the test set.

# Files

- [Forecast.xlsx](Forecast.xlsx): Contains the instructions for the challenge, the training set and the test set
- [Analysis File](subhankar_analysis.ipynb): Contains the analysis of the dataset and the solution to the challenge
- [Analysis HTML File](subhankar_analysis.html): Contains the HTML version of the analysis file
- [Requirements File](requirements.txt): Contains the list of packages required to run the analysis file

# Solution Summary

The solution to the challenge is divided into the following sections:
- Data Preprocessing: Since the dataset was in the xlsx format, the dataset was converted to csv format for both the training and test set.
- Exploratory Data Analysis: The training set was explored to get a better understanding of the dataset. Following analysis was conducted to know more about the dataset:
    - Basic Exploration: The rows and columns of the dataset were explored. It was noted that there were no null values in the dataset.
    - Data Distribution: An analysis was conducted to evaluate how many unique values were present in each column.
    - Exploring 'Sourcing Cost' (the target variable) Column: It was noted that the 'Sourcing Cost' column had negative values in the training dataset.
    - Temporal Analysis of Mean Training Sourcing Cost: The Mean Training Sourcing Cost was highest in the month of March and lowest in the month of November,
- Data Cleaning: This involved the following steps:
    - Exploration of Negative Values in 'Sourcing Cost' Column: The unique combinations of the first six dataset columns that had negative 'Sourcing Cost' was extracted and the distribution was plotted.
    - Imputation of Negative Values in 'Sourcing Cost' Column: The negative values in the 'Sourcing Cost' column were imputed using the mean of the positive 'Sourcing Cost' values for the unique combinations mentioned above.
- Feature Engineering: The following steps were performed on both the train and the test set:
    - Feature Extraction: The 'Date' column was split into 'Year', 'Month' and 'Day' columns.
    - Feature Encoding: The categorical columns were encoded using the LabelEncoder.
    - Metric: Mean Squared Error was used as the metric to evaluate the models.
    - Time Series Split: The Time Series Split was used to split the training set into training and validation set.
    - Cross Validation: The training set was split into 5 folds for cross validation.
- Model Training and Evaluation: The following ML models were trained and evaluated on the MSE metric:
    - GradientBoostingRegressor
    - XGBoost Regressor
    - LightGBM Regressor
- It was found that XGBoost Regressor Model performed the best on the test set.