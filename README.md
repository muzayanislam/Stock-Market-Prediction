
# 📊 Stock Price Prediction using LSTM

This project performs stock price prediction using historical stock data for major tech companies (**AAPL**, **GOOG**, **MSFT**, **AMZN**). It uses data from Tiingo and Yahoo Finance, applies LSTM neural networks for modeling, and forecasts future closing prices.



## 🔧 Tools & Technologies

- **pandas**, **numpy** – Data manipulation  
- **matplotlib**, **seaborn** – Data visualization  
- **yfinance**, **pandas_datareader** – Stock data fetching  
- **scikit-learn** – Data preprocessing (MinMaxScaler)  
- **TensorFlow Keras** – LSTM model building and training

## 📥 Data Collection

- Historical data for **Apple (AAPL)** is fetched using the **Tiingo API** and saved as a CSV.
- Additional stock data for **AAPL, GOOG, MSFT, and AMZN** is fetched from **Yahoo Finance** for the past year.

## 📚 Data Preparation

- Focus is on the **Close** price column for each stock.
- Data is normalized using `MinMaxScaler` to scale values between 0 and 1.
- A sequence of **60 previous days** is used as input to predict the **next day's** closing price.
- Data is reshaped to fit LSTM input shape: **(samples, timesteps, features)**.

## Model Training 

- Trained over **25 epochs** using **batch size = 32**  
- Training loss decreased steadily, indicating good learning

## 🔮 Prediction

- The model uses the last **60 days** of data to predict the **next 2 closing prices**  
- Predictions are then **inverse-transformed** to return them to the original price scale
