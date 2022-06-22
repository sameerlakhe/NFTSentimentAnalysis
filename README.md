# NFTSentimentAnalysis

## Background 
This project aims to analyze sentiments for a particular NFT collection and determine its correlation with price action.
An attemp was made to train a machine learning model (RNN LSTM) based on twitter data classified using Vader SentimentIntensityAnalyser.
However, due to the nature of the tweet data and most probably lack of data cleanup, the model was not identifying true positives correcly on the test data

This project generated real time sentiment analysis from Twits to determine the correlation with the closing price of the NFT Bored Ape Yatch Club collection over a one week period using Open Sea’s API key.


***The following approach was followed to generate sentiment analysis for an NFT collection and check its correlation to price action***
- Get twitter data for 1 week from Twitter using Tweepy API based on a query for an NFT collection i.e Boared APE Yatch Club (BAYC)
- Sanitize the data to remove emojis, special characters, mentions, hyperlinks
- User Vader SentimentIntensityAnalyser to get the sentiment of tweets 
- Classify the sentiment as positive/non-positive based on compound score >0.1
- Use this classified data for training the RNN LSTM model to classify future tweets
- The model did not do well, probably becuase of the type of data (short tweets with spelling mistakes and repeat texts), so it was not used further for analysis
- The price for the collection for 1 week was then fetched from OpenSea using API provided by OpenSea
- The sentiment and proce for the 1 week period were then plotted to identify correlation between the two

## Technology
* Twitter API Key
* Open Sea API Key 

## Installations
***This project uses the library tweepy to get the data from twitter***
pip install tweepy

## Example 
***BAYC (Boared APE Yatch Club) NFT Sample***
![BAYC.png](Images/BAYC_pics.png)

***World Cloud to indicate most common words in Tweets related to BAYC***
![WordCloud.png](Images/WordCloud.png)

***Classification Report of RNN LTSM model***
![RNN_LTSM_ClassificationReport.png](Images/RNN_LTSM_ClassificationReport.png)

***The ROC curve shows the trade-off between sensitivity (or TPR) and specificity (1 – FPR)***
![ROC_Curve.png](Images/ROC_Curve.png)

***Sentiment change for BAYC over 1 week period***
![BAYC_Sentiment_change.png](Images/BAYC_Sentiment_change.png)


***Price change for BAYC over 1 week period***
![BAYC_price_change.png](Images/BAYC_price_change.png)

***Correlation between Sentiment and Price of BAYC over 1 week period***
![Correlation_Price_Sentiment.png](Images/Correlation_Price_Sentiment.png)

***HeatMap to indicate correlation between Sentiment and Price for a 1 week period***
![HeatMap.png](Images/HeatMap.png)

## Findings

## Recommendations Going Forward

