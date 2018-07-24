# Sentiment-Bitcoin

## Language: Python (Jupyter Notebook)

Our project seeks to validate the correlations between Google search trends and Twitter sentiments with Bitcoin prices using recent data from 2017 and 2018. We are also interested to discover if these alternative data are predictive causes and whether they would be able to eﬀective forecast the value of Bitcoin. This research also seeks to expand beyond social media and web traﬃc data to include transaction data such as the daily usage of Bitcoin addresses.

In brief, our research takes a quantitative approach to:
1. Explore relationships between alternative data/factors (Google Trends interest levels, Twitter sentiments, Bitcoin exchange page views and BTC addresses used per day) and Bitcoin prices/returns.
2. Discover if these factors precede a rise or fall in the value of Bitcoin.
3. Transform our ﬁndings into a potential predictor of Bitcoin’s price

Data Collection
3.1 Bitcoin Market Data
Similar to traditional stock exchanges, bitcoins are traded on a bitcoin exchange in multiple ﬁat currencies or alternative cryptocurrencies. We have chosen to use exchange rates on Bitﬁnex (Bitcoin versus USD) as it is one of the largest cryptocurrency exchanges in the world. The data was obtained from the database Quandl for ease of collection and returns transformation using their API. Bitcoin prices are transformed into log returns and tested for stationarity using the Dickey-Fuller test to accommodate the required statistical properties for more accurate test results (e.g. Granger-Causality Analysis).

3.2 Google Search Interests
One source of alternative data would be in the form of web searches. Google is the most-used search engine on the World Wide Web and handles 3 billion searches each day. A free service called Google Trends displays how often a particular search-term is searched for relative to the total number of searches for their search engine. Our group selected the keyword “Bitcoin” and retrieved the weekly search interest data from the Google Trends API.

3.3 Twitter Sentiment Data
Twitter is a social media network which has grown rapidly as an important tool for businesses and individuals to share comments and information including ﬁnancial news and investment decisions. Prior research by Bollen, Mao and Zeng (2011) has shown that the emotional content of tweets can be useful in predicting market movements. As a rich source of real-time alternative data, sentiment of the information diﬀused through Twitter can be useful in determining the overall market perspective towards cryptocurrency and bitcoin.

3.3.1 Twitter historical data
For the collection of historical tweets within our speciﬁed timeframe, our team utilised a python library called “TwitterScraper” to retrieve a sample size of approximately 10,000 tweets a month based on the selected keywords “bitcoin” and “BTC”. We were able to extract a total of 152,293 tweets which were then ﬁltered by popular Bitcoin inﬂuencers to reduce the noise for a total of 38,936 tweets and resampled into weekly data for sentiment analysis.

3.3.2 Sentiment Analysis Tool – VADER
Valence Aware Dictionary and sEntiment Reasoner (VADER) is a lexicon and rule-based sentiment analysis tool suited towards analysing and quantifying social media text sentiments. The algorithm detects the polarity and intensity of sentiments in texts and generates a normalized sentiment score between -1 (most negative) and +1 (most positive). By putting the weekly resampled Twitter historical data through the sentiment analysis tool, we were able to derive the overall weekly Twitter sentiment based on the sample data retrieved.

3.4 Pageviews
Web traﬃc and pageviews can also be another source of alternative data. Pageviews record the total number of times a webpage is visited within a selected time period. Estimations of pageviews for Coinbase.com, a highly reputable bitcoin exchange, during the investigation period were downloaded using Alexa which is an analysis software developed by Amazon.com. The number of pageviews would be an indicator of the general trend of investors’ interests in bitcoin prices during the period.

3.5 Bitcoin Unique Address Used
To receive bitcoin payments, users are required to create Bitcoin addresses to direct payments from their counterparties. The number of bitcoin unique addresses used for each period can then be utilised as a measure of individual transaction data for that period. This information is provided by Blockchain.info which deals in Bitcoin statistics and market information, and retrieved using Quandl’s API.

Methodology
Despite earlier literature in 2015 reporting positive correlations between Google trend data and tweets’ sentiment with Bitcoin price, our research challenges if these ﬁndings still carry water with recent data and a longer time frame of study (1 January 2017 to 31 March 2018). On a more important note, what distinguishes our research from other paper is the fact that we use Bitcoin returns instead of price.

Prices are, unfortunately, not stationary and persistent of ‘shocks’ will be many in a non-stationary series. Shocks are evident in the price history of Bitcoin and as such we use Bitcoin returns that allow shocks to the system to gradually die away. This also eliminates any attribution to spurious regressions: if two variables are trending over time, a regression of one on the other could have a high R2 even if the two are unrelated. In addition, when running regressions, it is not possible to validly undertake hypothesis tests about the regression parameters if data are stationary. We then carried out the Augmented Dickey-Fuller test as conﬁrmation that Bitcoin returns follow a stationary process.
