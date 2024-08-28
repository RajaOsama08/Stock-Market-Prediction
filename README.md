# Stock-Market-Prediction

## Prerequisites Before running the code, ensure you have the following installed: 
 •	Python 3.6+
 •	pandas
 •	numpy
 •	scikit-learn
 •	xgboost
 •	tensorflow

**Overview**
This code is designed to perform various data processing, analysis, and prediction tasks on stock market datasets. Specifically, it loads stock price data for five different companies (Apple, Cisco, Intel, Nvidia, SAP), cleans and processes the data, visualizes important features, and uses machine learning models to predict the "Adjusted Close" price of the stocks.
**Functionalities**
**1.	Data Loading and Preparation:**
 •	Loading of five CSV files containing stock data for five companies.
 •	Displaying first few rows of each dataset to make sure that the data loaded successfully 
 •	Sets 'Date' column as index of the dataframes for timeseries analysis 

**2.	Data Visualization:**
 •	Adjusted Close Price Plot: Plots adjusted close price of the stocks against the time.
 •	Trading Volume Plot: Creates a grid of subplots of trading volume of each stock.
 •	Correlation Matrix: The correlation between different features such as Open, High, Low, Close, Adj Close, and Volume in the datasets are visualized as a heatmap.
**3.	Handling Missing Values:**
 •	Checks if any missing values exist in each dataset and also takes an argument to drop the rows containing NaN values.
**4.	Data Scaling:**
 •	The function MinMaxScaler scales the features, Open, High, Low, Close, and Volume of each dataset within the range of 0 to 1.
**5. Feature Scaling:**
 •	Defines the features Open, High, Low, Close, Volume, and defines the target variable Adj Close. 
**6.	Train-Test Split:**
 •	Further, the data is divided for each stock into training and test sets: 80% goes to train and 20% goes into the test.
**7.	 Modelling:**
 •	K-Nearest Neighbors (K-NN): Predicts the Adjusted Close price using KNN regressor in order to assess the model's performance with RMSE, MAE, MSE, and R².
 •	XGBoost: This algorithm utilizes an XGBoost regressor to predict the Adjusted Close price and then provides the performance of this model in terms of RMSE, MAE, MSE, and R². 
 •	LSTM-Random Forest (LSTM-RF): It combines the usage of an LSTM for extracting the time-series nature of the data with the usage of a Random Forest regressor on the job of forecasting the Adjusted Close price. 
    The mentioned metrics for evaluation include RMSE, MAE, MSE, and R².
**Input Data Format **
 •	File Type: CSV 
 •	Required Columns 
   •	Date: Date of the Stock Data (format: YYYY-MM-DD)
   •  Open: Opening price of the stock on the given date
   •  High: Highest price of the stock on the given date
   •  Low: Lowest price of the stock on the given date
   •  Close: Closing price of the stock on the given date
   •  Adj Close: Adjusted closing price accounting for splits and dividends
   •  Volume: Number of shares traded on the given date
**Output Data/Plots/Tables**
**1. Plots:**
 •	Adjusted Close Price Over Time: Line plot of the Adjusted Close price for all five stocks.
 •	Trading Volume: Grid of line plots showing the trading volume for each stock.
 •	Correlation Matrix: Heatmaps showing correlations between features.
**2. Tables:**
 •	Statistics: Summary statistics (mean, std, min, max, quartiles) for each stock dataset.
 •	Missing Values: Count of missing values in each dataset.
**3. Predictions:**
 •	K-NN, XGBoost, LSTM-RF: Model evaluation metrics (RMSE, MAE, MSE, R²) for each stock.

**Parameters and Hyperparameters**
**1. K-NN Regressor:**
 •	n_neighbors=5: Number of neighbors in the K-NN regression. 
**2. XGBoost Regressor:**
 •	Objective='reg:squarederror': Default loss function for XGBoost. 
 •	n_estimators=50: Number of boosting rounds. 
 •	learning_rate=0.2: Step size shrinkage for boosting. 
 •	max_depth=2: The maximum depth of trees.
**3. LSTM-RF Model:** 
  **LSTM:** 
   •	units=50: It is the number of LSTM units (neurons). 
   •	epochs=70: It is the number of training epochs. 
   •	batch_size=32: It is the number of samples per gradient update. 
  **Random Forest:** 
   •	n_estimators=100: It is the number of trees in the forest.
**Challenges and Issues**
1. Handle Missing Data: It was necessary that the data be devoid of missing value variances, which could further complicate the training of models. There was an option to drop NaN values for data integrity.
2. Handling Time-Series Data: The models were tuned for the appropriate treatment of the time-series data; most importantly, the LSTM model had to be prepared for creating sequence data for prediction.
3. Model Evaluation: The models were applied to unseen test data, which gave a good overview of the performance of the models; further tuning on hyperparameters may be required to produce better results.

**How to Use**
1. Data Preparation: Ensure the data files are in CSV format and include the required columns.
2. Run the Code: Execute each code line in your favorite Integrated Development Environment (IDE). The plots and model evaluation metrics will be displayed as the code runs.
3. Analyze Results: Go through the generated plots and metrics to get an idea about the performance of the stock and the models' fit.

Conclusion
This code provides a step-by-step approach toward the analysis and prediction of stock prices with the help of several machine learning models. From the above steps, you can run this code for your stock data and gain useful insights about the stock market.
