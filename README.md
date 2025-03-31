# LSTM-Based Stock Price Prediction 

Contributors:
- Dimple(055009)
- Rohan Jha(055057)

## Objective
The primary objective of this project is to develop and implement a Long Short-Term Memory (LSTM) neural network model to predict the closing prices of the NIFTY 50 stock market index. By analyzing historical time-series data, the model aims to forecast future price movements, providing valuable insights for investors and financial analysts. This predictive capability can assist in making informed decisions regarding stock trading and portfolio management. The project seeks to leverage the ability of LSTMs to capture long-term dependencies in sequential data, thus creating a reliable tool for financial forecasting.

## Data Description
### 1. Source
The historical data for the NIFTY 50 index was obtained using the `yfinance` library in Python. The ticker symbol `^NSEI` was used to download the data.

### 2. Timeframe
The dataset covers a 20-year period, ranging from **January 31, 2005, to January 31, 2025**.

### 3. Features
The primary feature used for analysis and prediction is the **"Close"** price of the NIFTY 50 index. This represents the final trading price at the end of each day.

### 4. Preprocessing
- **Normalization**: The "Close" price data was normalized using the `MinMaxScaler` from `scikit-learn`. This scaled the values to a range between **0 and 1**.
- **Purpose**: Normalization helps improve model training by ensuring that all input features are on a similar scale, preventing features with larger values from dominating the learning process.

### Sample Data:
| Date       | Close Price |
|------------|-------------|
| 2007-09-17 | 4494.649902 |
| 2007-09-18 | 4546.200195 |
| 2007-09-19 | 4732.350098 |
| 2007-09-20 | 4747.549805 |
| 2007-09-21 | 4837.549805 |

## Observations
### 1. Data Trends
The NIFTY 50 data exhibits **trends and patterns** over the 20-year period, including periods of growth, stagnation, and volatility influenced by economic events and market sentiment. These trends are observable by plotting the closing prices over time.

### 2. Normalization Impact
The use of `MinMaxScaler` effectively scaled the data between **0 and 1**, which is crucial for the LSTM model's performance. Normalized data ensures **faster convergence** during training and prevents issues caused by large differences in the magnitude of the input values.

### 3. Model Architecture
The notebook file includes the import statements for building the **LSTM model**, implying the intention to use layers such as:
- **LSTM units** for capturing sequential dependencies.
- **Dropout layers** for regularization.
- **Dense layers** for output prediction.

A typical architecture includes the following components:
```python
model = keras.Sequential([
    keras.layers.LSTM(50, return_sequences=True, input_shape=(X_train.shape[1], X_train.shape[2])),
    keras.layers.LSTM(50, return_sequences=False),
    keras.layers.Dense(25),
    keras.layers.Dense(1)
])
```

## Managerial Insights
### 1. Predictive Capabilities
The LSTM model has the potential to **forecast future closing prices** of the NIFTY 50 index, assisting investors and financial analysts in making **informed decisions**. The accuracy of these predictions depends on the model's **architecture, training data, and hyperparameter tuning**.

### 2. Risk Management
By analyzing **predicted trends**, portfolio managers can **identify potential market downturns or upswings**, allowing them to adjust their portfolios to **mitigate risk** or capitalize on opportunities. 
- **Early warnings** of potential downturns can help reduce losses.
- **Identifying upward trends** can enhance returns.

### 3. Strategic Decision-Making
Financial institutions can incorporate this model into their **decision-making frameworks** to optimize **trading strategies**. Algorithmic trading systems can be designed to **execute trades based on the model's predictions**, improving efficiency and potentially increasing profitability.

### 4. Potential Improvements
The model's performance can be further improved by incorporating:
- **Additional features**, such as trading volume, macroeconomic indicators (e.g., inflation rates, GDP growth), and sentiment analysis from news articles and social media.
- **Ensemble methods**, combining multiple models for better accuracy.
- **Fine-tuning hyperparameters**, such as the number of LSTM layers, dropout rate, and learning rate.
- **Continuous retraining**, incorporating more recent data to keep the model relevant.

## Conclusion
This report provides a detailed overview of the **LSTM stock price prediction project** based on the notebook file, including the **objective, data description, observations, and managerial insights**. The inclusion of **code snippets and potential enhancements** offers a more comprehensive understanding of the project's scope and potential.
