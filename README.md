# Department-wise-Sales-Prediction
Files Structure:

Sales Prediction.ipynb: Contains the Dept-wide-sales for each store project code
Effects_of_Markdown_and_Weekly_sales.ipynb:contains the weekly_sales prediction for each store project code
Utilities: Contains my own custom modules for evaluation metrics(EvaluationMetrics.py) and visualization(Visualizations.py)
Data: Contains the 3 data(.csv) files.
Project Details
We have been given historical sales data for 45 stores situated in various regions. Each store comprises multiple departments, and our objective is to forecast sales for each department within these stores.

Furthermore, stores organizes several promotional markdown events during the year. These markdowns coincide with significant holidays, with the four most significant ones being the Super Bowl, Labor Day, Thanksgiving, and Christmas. The weeks encompassing these holidays carry five times more weight in the evaluation compared to regular weeks. One of the challenges we face in this competition is modeling the impact of markdowns during these holiday weeks when we don't have complete or ideal historical data.

.This dataset comprises of data from several files

stores.csv

This file contains anonymized information about the 45 stores, indicating the type and size of store.

sales.csv

This is the historical training data, which covers to 2010-02-05 to 2012-11-01. Within this file you will find the following fields:

Store - the store number
Dept - the department number
Date - the week
Weekly_Sales - sales for the given department in the given store
IsHoliday - whether the week is a special holiday week
features.csv
This file contains additional data related to the store, department, and regional activity for the given dates. It contains the following fields:

Store - the store number
Date - the week
Temperature - average temperature in the region
Fuel_Price - cost of fuel in the region
MarkDown1-5 - anonymized data related to promotional markdowns that Walmart is running. MarkDown data is only available after Nov 2011, and is not available for all stores all the time. Any missing value is marked with an NA.
CPI - the consumer price index
Unemployment - the unemployment rate
IsHoliday - whether the week is a special holiday week
For convenience, the four holidays fall within the following weeks in the dataset (not all holidays are in the data):

Super Bowl: 12-Feb-10, 11-Feb-11, 10-Feb-12, 8-Feb-13
Labor Day: 10-Sep-10, 9-Sep-11, 7-Sep-12, 6-Sep-13
Thanksgiving: 26-Nov-10, 25-Nov-11, 23-Nov-12, 29-Nov-13
Christmas: 31-Dec-10, 30-Dec-11, 28-Dec-12, 27-Dec-13

**Methodology**

Exploratory data analysis
Visualized the distribution of weekly sales (target variable) and numerical features using histograms. Utilized count plots to display category-wise distributions.
Generated a plot showcasing the variation in median weekly sales across categories within the categorical input feature.
Depicted relationships between all numerical features and weekly sales through scatter plots.

**Data Preprocessing**
Removed duplicate rows, handled null values and removed rows with negative weekly sales.
Performed one-hot encoding to encode categorical features and used feature engineering to take Thanksgiving and Christmas weeks into account.
Removed outlier data from numerical features.

**Data Manipulation**
Split data into training and test set with 20% of data being held out for testing.

**Feature Selection**
Checking for correlation among features and removing correlated features.
Used PermutationImportance to select the numerical features.
Feature Scaling
Performed feature scaling using StandardScaler()
Predictive Modelling
Applied the below models with hyperparameter tuning using GridSearchCV:

SGD Regressor()
Extratreeregresssor()
Model Evaluation
Used the below metrics to compare the model's performance on test set:

R-squared
Root Mean Squared Error(RMSE)
output submission
After the model prediction successfully,convert to csv file as a output.
