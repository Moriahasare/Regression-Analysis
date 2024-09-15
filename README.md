# Regression-Analysis

Welcome to the **Time Series Forecasting Project**. The aim is to predict store sales using data from Corporation Favorita, a major grocery retailer in Ecuador, using Machine Learning techniques.


## Project Scenario
Every business aims to boost its revenue or profit margin, and one important area where industry participants concentrate their efforts is client retention. The majority of businesses in today’s machine learning environment use forecast models utilising time series analysis to determine how to handle client demand or prevent losses.

### Overview
Scenario: As a data scientist in Corporation Favorita, a large Ecuadorian-based grocery retailer. Corporation Favorita wants to ensure that they always have the right quantity of products in stock. To do this I have decided to build a series of machine learning models to forecast the demand of products in various locations. The marketing and sales team have provided you with some data to aid this endeavor. Your team uses CRISP-DM Framework for Data Science projects


## Project Description

The goal of this project is to develop a time series regression model to accurately predict the unit sales of various items sold at Corporation Favorita's stores across different locations in Ecuador. The model aims to optimize inventory management by forecasting future demand, enabling the company to maintain optimal stock levels and minimize both overstocking and understocking situations. By leveraging historical sales data along with additional features such as promotional status, store information, and product details, the model will provide actionable insights to aid in strategic decision-making and improve overall operational efficiency.


### Data for the project
The training data includes dates, store, and product information, whether that item was being promoted, as well as the sales numbers. Additional files include supplementary information that may be useful in building the models

Follow link for data [GOOGLE DRIVE](https://drive.google.com/drive/folders/1oZu0R8McobPgOjksMME4vkHiw_c6_W3N?usp=drive_link).


| **Dataset** | **Description** |
|------------|-----------------|
| train.csv  | Training data containing time series of features store_nbr, family, and onpromotion, as well as the target sales. |
|            | - `store_nbr`: Identifies the store where the products are sold. |
|            | - `family`: Identifies the type of product sold. |
|            | - `sales`: Total sales for a product family at a specific store on a given date (can be fractional). |
|            | - `onpromotion`: Total number of items in a product family that were being promoted at a store on a given date. |
| test.csv   | Test data with the same features as the training data. Predict target sales for these dates. |
| transaction.csv | Contains date, store_nbr, and transactions made on specific dates. |
| sample_submission.csv | Sample submission file in the correct format. |
| stores.csv | Store metadata, including city, state, type, and cluster. |
|            | - `cluster`: Grouping of similar stores. |
| oil.csv    | Daily oil price data, including values during both the train and test data timeframes. |
| holidays_events.csv | Holidays and events data, with metadata. |


## `Hypotheses`

`Null Hypothesis`: The payment of wages in the public sector on the 15th and last days of the month does not influence store sales.

`Alternate Hypothesis`: The payment of wages in the public sector on the 15th and last days of the month significantly influences store sales.

## Results
alpha = 0.05
t-statistic: 0.4424065109693579
Critical t-value: 1.9613753699116634

Fail to reject the null hypothesis. There is no significant difference in average store sales between payday and non-payday days.


## ✍️Data Understanding
The data was pulled from the following various sources:
- data from a Github repository
- data from a OneDrive 
- data from a remote database

Data from the Github repository and SQL database data sets were used in this project for training and evaluation the machine
learning model while the last data set was used for testing the accuracy of the model.

Some additional tables acted as supplements for providing extrwa information

The major libraries used for this project were:
 1. Data manipulation: NumPy, pandas
 2. Data visualisation : Matplotlib, Seaborn, Plotly
 3. Machine learning methods : Sklearn, XGBoost, CatBoost, Linear Regression
 4. Statistical models : ARIMA, SARIMA


# 🏋️‍♀️Data cleaning

The first phase of the cleaning aspect checked for duplicates, nulls, mismatched columns, data coherency, datatypes and column names

There were some observations which included:

- null values present in the following columns: some dates were missing
- the datatype of date being strings or integers
- there are no duplicates in the concatenated stage

 
In general, not much cleaning was required for the dataset. Highlights of the cleaning process include:
 - Converting to the appropriate datatypes
 - Using the tools to fill in blank dates in order to maintain data coherency

The time series nature of this project necessitated a sequential approach for optimal efficiency. Consequently, traditional techniques did not apply to certain steps, such as filling in missing values or testing and training data for model construction.This is true of the models that are employed as well.



## Project Preview

The project includes the following stages:

### 1. 📥 Data Collection

- Azubi Africa's SQL Server database, GitHub repository and OneDrive.

N/B: The datasets from the sources above are saved in the google drive link [GOOGLE DRIVE](https://drive.google.com/drive/folders/1oZu0R8McobPgOjksMME4vkHiw_c6_W3N?usp=drive_link).

### 2. 📚 Data Loading

- Utilizing `pyodbc` for SQL data
- Leveraging `pandas` for CSV and Excel files

### 3. 💡 Exploratory Data Analysis (EDA)

- Merging
- Duplicate checks
- Handling missing values
- Renaming Columns and Changing Datatypes
- Creating new features
- Visualizations
- Hypothesis testing
- ADF Testing

### 4. 📈 Answering Questions with Visualizations

**Questions:**

Visualisations were produced based on the analytical questions asked. These visuals were paramount to providing a solid foundation for analysising any trends or hitting patterns in analysing the factors contributing to churn analysis

 Business Questions
1. Is the train dataset complete (has all the required dates)?
2. Which dates have the lowest and highest sales for each year (excluding days the store was closed)?
3. Compare the sales for each month across the years and determine which month of which year had the highest sales.
4. Did the earthquake impact sales?
5. Are certain stores or groups of stores selling more products? (Cluster, city, state, type)
6. Are sales affected by promotions, oil prices and holidays?
7. What analysis can we get from the date and its extractable features?
8. Which product family and stores did the promotions affect.
9. What is the difference between RMSLE, RMSE, MSE (or why is the MAE greater than all of them?)
10. Does the payment of wages in the public sector on the 15th and last days of the month influence the store sales.

**Visualization Tools:**

- Matplotlib
- Seaborn

### 5. ⚙️ Feature Engineering

- Data Splitting
- Feature Encoding with OneHotEncoder
- Feature Scaling with MinMaxScaler

### 6. ⌛ Model Training

- Linear Regression
- XGBoost
- CatBoost
- AutoReg
- ARIMA
- SARIMA (was not utilised because of computational resources)

### 7. 📊 Model Evaluation

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Squared Logarithmic Error (MSLE)
- Root Mean Squared Logarithmic Error (RMSLE)

### 8. 🎯 Hyperparameter Tuning

- RandomSearchCV

### 9. 🤔 Prediction on Validation Set

### 10. 📒 Prediction on Test Dataset

### 11. 💭 Exportation

- os
- pickle
- save_model

## Observations

CatBoost outperforms the other models across all metrics, making it the best choice for your dataset. It produces the most accurate predictions with the smallest errors

## Installation and Setup 🔧

To get started with this project, you'll need to install the following Python packages using `pip`:

```bash
pip install pyodbc sqlalchemy lightgbm catboost python-dotenv pandas numpy matplotlib seaborn scipy pmdarima
```

Make sure to have these packages installed before running the project.
Follow these steps for installation:

1. Clone this repository to your local machine.
2. Install the required Python packages using pip:
   ```bash
   pip install -r requirements.txt
   ```

You're now ready to dive into this exciting data journey!

## Author 👨‍💼

This project was built by **Moriah Asare**.

Here are my details:


| Detail | Link |
| ------ | ---- |
| Email | moriahasare@gmail.com |
| LinkedIn | [Moriah Asare](www.linkedin.com/in/moriah-asare) |
| GitHub | [Moriahasare](https://github.com/Moriahasare/Regression-Analysis.git) |
| Medium | [Moriah Asare](https://medium.com/@moriahasare/time-series-regression-analysis-be9d97ec0fca) |`


## License

The MIT Licence governs the use of this project. Details can be found in the LICENCE file.

