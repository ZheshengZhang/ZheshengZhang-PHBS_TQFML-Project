# LSTM-based method for stock returns prediction and trading strategy

Team member:  Zhesheng Zhang  (individual)

## Environment
Python 3.6
TensorFlow 1.3.0 (the version is very important since the TensorFlow package may change a lot in different versions)

## Basic method
In LSTM model for stock prediction, one sequence was defined as a sequential collection of the daily dataset of any single stock in a fixed time period (N days). The daily dataset describes the performance of the stock with sequence learning features like closing price, trade volume on one particular day in these N days. 

## Raw Data Set and Clean data
All A share stocks from 2004 Jan.2 to 2018 Jan.4 including open,close,high and low daily prices, trade volume and turnover rate. We choose 4 typical stocks and merge all the features data, then clean the data with cleaning.ipynb. The final data will be saved as 'stock_code.csv'

## Brief plan
By using LSTM method, we plan to get stock return prediction and try to find good features in predicting stocks trend in several days. And I make a simple trading strategy by considering whether the predicted return will be postitive the next day. It will give us a buying or selling signal. I compared the strategy net value by the real stock net value.

## Reference
1.Krollner, Bjoern, Bruce Vanstone, and Gavin Finnie. "Financial time series forecasting with machine learning techniques: A survey." (2010).  

2.Chen, K., Zhou, Y., & Dai, F. (2015). A LSTM-based method for stock returns prediction: A case study of China stock market. IEEE International Conference on Big Data (pp.2823-2824). IEEE.
