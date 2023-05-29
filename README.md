# 1. Introduction

This research explores the use of sentiment analysis on Twitter data to predict Bitcoin prices, addressing a gap in understanding how sentiment influences the highly volatile cryptocurrency market. The study adopts a recurrent neural network model, particularly LSTM, along with the VADER sentiment analysis tool, integrating tweet sentiment scores with historical Bitcoin data. These findings could provide valuable insights for investors and researchers alike about the impact of social media on cryptocurrency fluctuations.

# 2. System design

<img width="348" alt="image" src="https://github.com/jasper1005/Analysing-the-Sentiment-of-Twitter-Data-on-the-Bitcoin-by-LSTM/assets/69462492/6efea9e1-afd6-45be-a4c4-5ab228fa8b38">

The design of the LSTM prediction model with sentiment analysis had been divided into an end-to-end architecture which shows in Figure 1. Firstly, plenty of research shows that sentiment analysis would affect the result of the recurrent neural network model to predict the financial market. Therefore, the sentiment data had been extracted from the related Tweets, which were collected by Twitter API. Also, the historical Bitcoin market data will be collected by Kaggle. Secondly, the tweets data cannot be direct merged with the Bitcoin market data. Thus, the collected tweets' textual data is required for pre-processing such as deleting all unnecessary data, removing the duplicated content, and cleaning the stop word from the sentences. Thirdly, the social media data had been classified as sentiment polarity for analysing the sentiment score, and the calculated sentiment data had been saved independently with date and time. Fourthly, the time of the collected Bitcoin market data is a timestamp format instead of a date and time format, which is not matched the sentiment data. Hence, the pre-processing of the historical data is needed. Fifthly, the LSTM model has required to set up the level of layers and the number of nodes. Therefore, the LSTM model in this part had been adjusted for obtaining better results. Sixthly, Twitter sentiment data is embedded in the original Bitcoin market data that is matched by time and date, and both merged data and original data are used as input for the prepared machine learning model. Seventhly, the prediction models' output had been plotted for visualizing the result. Finally, the result of both two had been compared for discovering the effectiveness of the sentiment data.

# 3. Data Collection

For feeding the data into the model of this project, there are two primary data that had been collected by web scraping, which are the Bitcoin-related tweets and Bitcoin market data (minutely). The selected period of the collected Bitcoin market data and Twitter data is from 1 July 2022 to 30 July 2022.

-  Twitter data: Twitter API had been applied to extract tweet content by hashtags. For example, the symbol of Bitcoin is BTC, therefore, the tag #BTC was used for searching the related tweets on Twitter. To collect the data within a certain period, the academic research account from the Twitter developer portal had been applied. Afterward, there are two more related functions that can be used. One of the Twitter API's premium functions is called "search_30_days", which just permits a user to collect a maximum of 250 requests and 25000 tweets per month. Based on the limitation of that function, the project collected the data for exactly the month of July 2022. Finally, the number of extracted tweets is 29762 and the size of the data is approximately 4 MB. The originally extracted tweets data contained username, number of followers, number of friends, tweet content, length of the tweet, tweets ID, date, time, lang, number of likes, and number of retweets.

-  Historical Bitcoin market data: Originally, the dataset of minutely Bitcoin historical data was planned to extract by the Yahoo! Finance API. However, the API function for getting market data minutely had been deleted by them. To solve this problem, the alternative dataset had been collected from the Kaggle dataset called "400+ cryptocurrency pairs at 1-minute resolution". the collected data related to BTC-USD is from 2013-04-01 to 2022-08-02, which covered the selected period of this project. The data contain some information such as time, open, close, high, low, and volume. Among these, all the prices inside the dataset had been represented by USD dollars. Also, the format of representing the time is a timestamp format instead of a date-time format.

# 4 Finding

The project uses Twitter sentiment data to predict stock market values, but the LSTM neural network's prediction accuracy with sentiment data was not significantly improved. Two potential issues were identified. First, the collected sample size of 40 tweets per hour may not sufficiently represent the time series data's complexity. Increasing the data amount and collection period might lead to more meaningful results. Second, the VADER model's sentiment scores, which are based on individual words, may not accurately capture a sentence's complete sentiment. Thus, the effectiveness of sentiment data for improving cryptocurrency prediction couldn't be conclusively proven in this study.

# 5 Limitation

There is plenty of limitation in the data collection, which is restricted by the API limitation and the cost of upgrading the API. First, the Twitter API “search_tweets” function is not allowed users to send too many requests to extract the data within 15 minutes, and every request of the search function is only allowed for 100 tweets. Furthermore, only the data within 7 recent days permit extraction. Therefore, another function from Twitter API called “search_30_days” had been selected. However, this function also exists a lot of limitations. The search_30_day function is a premium function that can only allow enterprise and academic users to access it. Even though the permit had been successfully proved by the developer platform admin, the free academic version is not allowed to collect the data easily. The restrictions of the free version called “Sandbox” can only retrieve the date within 30 days, and a monthly quota of requests is 250 and a monthly quota of tweets is 25000. The developer portal provided a button for upgrading the package from Sandbox to Premium, but the price of upgrading the service cost up to $2499 USD, which is extremely expensive. Therefore, based on the limitation, the tweet can only extract hourly and 40 tweets for every hour.

# 6 Summary

The result of the project had been mentioned in the first part, which discussed the result of the project had no significant difference but the correlation between sentiment data and market data existed. Therefore, the possible issues of the dataset collected from Twitter and the discovery of the project had been listed in the chapter of Finding. In the first place, due to the limitation of the Twitter API, the sample size of the tweet is not tight and large enough, and the time series data cannot directly apply a statistical theory called CLT because of the data type difference. In the second place, the VADER is a word-based sentiment analysis tool instead of a sentence-based sentiment analysis tool, which means the meaning of a sentence may be misinterpreted by the tool. Finally, the limitation of Twitter API had been detailly explained such as the request and tweet extract limitation, the account restriction etc.






