# NFTSentimentAnalysis

## Background 
This project aims to analyze sentiments for a particular NFT collection and determine its correlation with price action.
An attempt was made to train a machine learning model (RNN LSTM) based on twitter data classified using Vader Sentiment Intensity Analyzer.
However, due to the nature of the tweet data and most probably lack of data cleanup, the model was not identifying true positives correcly on the test data.

This project generated real time sentiment analysis from Twits to determine the correlation with the closing price of the NFT Bored Ape Yatch Club collection over a one week period.


**The following approach was followed to generate sentiment analysis for an NFT collection and check its correlation to price action.**
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

## Resources

## Installations
***This project uses the library tweepy to get the data from twitter***
pip install tweepy

## Usage Examples 
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
* The correlation we found was not clear/strong
* Our Hypothesis was that there would be a positive sentiment as prices went up. (And vice versa)
* But what we found is that we had insufficient data to determine any correlation.
* There are many different ways to approach this task, but they require time to test and validate the results and see what works and what doesn’t - that probably would require more than two weeks. The good news is that we were able to see the full process required to get the API key, see all the options available, pull the data, run the model, and understand the pros and cons of different types of tweets. For example the approach of using hashtags (#NFT, #BAYC) can be one of the purest ways to gather people’s sentiment, but there is significant effort required to clean up the data, whereas we could use specialized publications with language that is more polished, similar to what we used in class, but with a potentially distorted view of client sentiment in real time, which in the end is what we are trying to understand.
This does not mean that the RNN LSTM model was not good, but it was probably not the best approach for us considering the time and resources available, but with some extra time the model could have been a good choice.

## Recommendations Going Forward
In order to continue improving this tool, we could explore other methods above and beyond what we’ve already used, for example: 
* Use ngrams to read sentiment via sequencing of words.
* Invest time cleaning up and classifying twits manually, the challenge with this is that its could be very time consuming to go through thousands of twits, and we would need to be very careful to make sure our personal biases do not affect the results of the classification exercise
* Take NFT pricing to another level and use Machine Learning to try to predict future valuations of NFT collections, in combination with Sentiment analysis to reach a more reliable future valuation. Machine learning models could be particularly helpful here considering that many NFT collections don’t have a lot price history.
* Incorporate additional data sources to our analysis to make it more accurate and complete: for example adding Discord, Articles, or curating a list of hashtags, NFT publications , and key influencers to try to present a balanced view of NFT sentiment.
* We used one week of data for this test, but next steps for us would include expanding our time horizon to cover a longer period of time
* Finally once we have a solid model that we feel is more accurate, we would replicate it to other collections beyond BAYC. (Doodles, Mutant Ape Yatch club, Crypto punks , etc)

## Contributors
Chantal Garnett

Sameer Lakhe

Emiliano Mendez

Marcus Policicchio 



