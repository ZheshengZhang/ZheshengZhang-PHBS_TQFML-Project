# LSTM-based method for stock returns prediction and trading strategy

Team member:  Zhesheng Zhang  1601213664

## Environment
Python 3.6  
TensorFlow 1.3.0 (the version is very important since the TensorFlow package may change a lot in different versions，it will run error in other versions)

## Long Term Short Memory  
Traditional RNN 
![RNN_unrolled](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/raw/master/images/RNN-unrolled.png) 

Long Term dependency problem  
![RNN_unrolled](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/raw/master/images/RNN-longtermdependencies.png) 

RNN structure  
![RNN_unrolled](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/raw/master/images/LSTM3-SimpleRNN.png) 

LSTM structure
![RNN_unrolled](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/raw/master/images/LSTM3-chain.png) 
  
Reference:    [http://colah.github.io/posts/2015-08-Understanding-LSTMs/](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)


## Basic method
In LSTM model for stock prediction, one sequence was defined as a sequential collection of the daily dataset of any single stock in a fixed time period (20 days). The daily dataset describes the performance of the stock with sequence learning features like closing price, trade volume on one particular day in these 20 days. The prediction target will be today's return rate (regression model) or whhether the return is positive (classification model).

## Raw Data Set and Clean data
All A share stocks from 2004 Jan.2 to 2018 Jan.4 including open,close,high and low daily prices, trade volume and turnover rate. We choose 4 typical stocks and merge all the features data, then clean the data with [cleaning.ipynb](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/blob/master/cleaning.ipynb). The final data will be saved as 'stock_code.csv'  

### features  
1.  Open price  
2.  Close price  
3.  High price  
4.  Low price  
5.  Trade Values  
6.  Turnover

tips:    Here the all A shares data is too big, so I didn't upload them.

## My trading strategy
Since we have predicted the return, we make simple trading strategy:  
If the predicted return tomorrow is positive, you are buying or still owing the stock by the end of closing  
If the predicted return tomorrow is negative, you are selling or keeping no shares by the end of closing  

Tips:1.we consider the trading cost as 0.3%  
     2.The buying or selling price is close to the ClosePrice that day  

## Result Analysis
I choose 4 typical stocks to analysis
1.  600519.SH  MouTai  "White Horse" stock  [result_analysis1.ipynb](https://github.com/ZheshengZhang/ZheshengZhang-PHBS_TQFML-Project/blob/master/result_analysis1.ipynb)  



2.  600019.SH  BaoGang  Strong cyclical stock
3.  601398.SH  ICBC  Bank stock
4.  300431.SZ  BaoFeng Tech.  "Demon" stock，abnormal stock



## Reference
1.Krollner, Bjoern, Bruce Vanstone, and Gavin Finnie. "Financial time series forecasting with machine learning techniques: A survey." (2010).    
2.Chen, K., Zhou, Y., & Dai, F. (2015). A LSTM-based method for stock returns prediction: A case study of China stock market. IEEE International Conference on Big Data (pp.2823-2824). IEEE.
