# etl-customer-pipeline
Automated ETL pipeline for customer behavior data using Python
# ETL-Pipeline-Customer-Behavior

Link to dataset source: https://www.kaggle.com/code/youssefabdelghfar/e-commerce-customer-behavior/notebook

## Library Imports and Setup:

Imports Python libraries including `pandas` and `matplotlib`. These are used for:
- Extracting raw data from files
- Transforming data by encoding and engineering new features
- Visualizing customer engagement patterns

## Data Loading:

- Loads the original dataset (`E-commerce.csv`) using pandas
- Displays basic information about the dataset: data types, shape, and sample records
- Checks for missing values using `.isnull().sum()`

## Preprocessing:

- Fills missing values in the `Satisfaction Level` column with `'Unknown'`
- Encodes categorical variables for modeling and analysis:
  - `Gender` → 0 (Male), 1 (Female)
  - `Membership Type`, `City`, and `Satisfaction Level` → encoded using `pd.factorize()`
- Ensures the dataset is numerically structured for further analysis

## Feature Engineering:

Two new meaningful features are created:
- `Spend_Per_Item` = `Total Spend / Items Purchased`  
  → Gives insight into spending efficiency per customer

- `Engagement_Score` = `Average Rating / (Days Since Last Purchase + 1)`  
  → Quantifies recent activity combined with customer feedback

## Transformation Output:

- The final transformed DataFrame is saved as `transformed_customer_behavior.csv`
- This version is cleaned, numerically encoded, and feature-rich
- It serves as a base for any downstream machine learning or BI process

## Visualization:

- A scatter plot is created:
  - X-axis: `Spend_Per_Item`
  - Y-axis: `Engagement_Score`
- This visual explores the correlation between spending behavior and customer engagement

## Prediction and Output:

- Prediction is not the focus in this project.
- Instead, the output is a fully prepared dataset suitable for prediction tasks like:
  - Churn classification
  - Customer segmentation
  - CLTV estimation

## Error Handling:

Basic error handling (optional) includes:
- Handling missing data
- Preventing divide-by-zero during feature creation
- Catching file reading errors

## Project Summary:

This project builds an automated ETL pipeline that processes raw customer behavior data into a structured format.
