# xgboost-stock-model
Using XGBoost to Predict Stock Return in Hang Seng Index

Predicting stock return using machine learning algorithms has various advantages comparing with traditional linear algorithms. 

XGBoost is an algorithm that has recently been dominating applied machine learning and Kaggle competitions.

I will demonstrate the whole workflow from getting data to generating trade file in this repository.

<a href="https://github.com/kymanj/xgboost-stock-model/blob/master/Scrape%20HSI%20Constituents.ipynb">Scrape HSI Constituents.ipynb</a> will scrape cleaned universe data from Hang Seng Index official website. Latest constituents and historical change in constituents will be scraped and stored in <a href="https://github.com/kymanj/xgboost-stock-model/tree/master/HSI%20Cons">HSI Cons</a> folder. Finally, <a href="https://github.com/kymanj/xgboost-stock-model/blob/master/hsiUniverseDf.csv">hsiUniverseDf.csv</a> will be created based on two scraped files in the folder. Selenium with Firefox webdriver will be used because we need to scrape JavaScript items. 

<a href="https://github.com/kymanj/xgboost-stock-model/blob/master/Get%20Price%20and%20Volume%20Data%20then%20Calculate%20Simple%20Factors%20for%20HSI.ipynb">Get Price and Volume Data then Calculate Simple Factors for HSI.ipynb</a> will get price and volume data from Yahoo based on the universe in <a href="https://github.com/kymanj/xgboost-stock-model/blob/master/hsiUniverseDf.csv">hsiUniverseDf.csv</a>. Then, a list of factors will be created based on price and volume data. Finally, <a href="https://github.com/kymanj/xgboost-stock-model/blob/master/hsiFactorDf.csv">hsiFactorDf.csv</a> and <a href="https://github.com/kymanj/xgboost-stock-model/blob/master/hsiReturnDf.csv">hsiReturnDf.csv</a> will be created. These two files will be the X (factor) and Y (return) in our XGBoost model.

<a href="https://github.com/kymanj/xgboost-stock-model/blob/master/Predicting%20Stock%20Return%20using%20XGBoost.ipynb">Predicting Stock Return using XGBoost.ipynb</a> will use XGBoost to predict Y (return) by X (factor). It's just a simple example to demonstrate how to utilize XGBoost in stock return prediction by using the same months in the past 7 years to predict the return pattern in this month. Detailed elaboration will be included in the notebook. In fact, tons of modifications could be made to improve the simple model that I demonstrated in this script. Reason of choosing XGBoost and Methodology to normalise features will be discussed as well. Finally, a model trade file named <a href="https://github.com/kymanj/xgboost-stock-model/blob/master/hsiSeasonModel7.csv">hsiSeasonModel7.csv</a> will be created.
