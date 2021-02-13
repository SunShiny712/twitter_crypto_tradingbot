# Tweet Activated Crypto Trader

### Feb 11th 2021 - has been tested on DOGE/BTC (Kraken & Binance), DOGE/GBP, BTC/GBP (Binance), successfully made a 17% & 3% return from Elon's latest Doge tweets

The idea is to buy crypto using a Twitter trigger and sell after a user specified time / price / % gain e.g. when Elon musk tweets about Dogecoin

Markets, particularly small market cap altcoins are heavily influenced by individuals with large following 'hyping' up a cryptocurrency, crypto pumps. We can capitalize on this opportunity by being one of the first to exectue trades when a tweet is posted

When a Tweet is posted, it checks for substring matches with keywords for a particular cryptocurrency

These keywords and coins can be user specified

To configure on local system: \
`pip install -r requirements.txt`

To run with Binance: \
`python twitter_binance.py`

To run with Kraken: \
`python twitter_kraken.py` 

API keys are kept in a json directory up from repo ../keys.json
`{\
	"twitter_keys" : {\
		"consumer_key": "XXXXXXXXXXXXXXXXXXXX",\
		"consumer_secret":"XXXXXXXXXXXXXXXXXXXX",\
		"access_token_key":"XXXXXXXXXXXXXXXXXXXX",\
		"access_token_secret":"XXXXXXXXXXXXXXXXXXXX"},\
	"binance_keys":{\
		"api_key":"XXXXXXXXXXXXXXXXXXXX" ,\
		"secret_key":"XXXXXXXXXXXXXXXXXXXX"\
	}\
}`

## To Do
- User input parameters (done)
- Error handling if trade is unclosed (done)
- Fully implement Binance (lower taker/maker fees - 0.01% compared to Krakens 0.26%) (done)
- Trade logging json mechanism (done)
- Verify working using BTC transactions (done)
- Reduce latency between tweet and trade from 2s to < 1s (done)
	- Look at streaming Twitter rather than querying every second (slower ~ 5s))
		- Integrate streaming
	- Selenium scraper (slow)
	- Requests module (doesn't work with Twitter)
- Get a list of accounts to follow and trade ideas
- Handle Retweets vs. Tweets (done)
- Transfer list of keywords to text file
- Test for multiple other alt coins
	- Test when ticker symbols are reversed
- Work out the amount to buy for each alt
	- Find a reasonable amount to trade based of previous exchange rates in £/$
	- Keep a list of exchange rates in mem or in text file and update a a certain freq / at the start
- Implement for any alt coin if listed on Binance or Kraken
- Mechanism for pulling out of all positions
- Backtest Notebook to backtest ideas
- Implement sell options
	- Specified % gain
	- Limit order at a price target
	- Trailing stop losses
- Position size as a fraction of the max
	- Based on particular keyword
	- Based on tweet type
	- Based on time since last tweeted about
	- Based on sentiment
- Machine Learning features
	- Implement sentiment feature
		- For size of position 
		- Shorting 
	- Look at interpreting images (CV for text extraction, object detection on memes) 


## Notes
- Requires a Twitter Developer API detecting tweets through Tweepy
- Requires a crypto exchange (Kraken/Binance) API which is used through ccxt
	- Uses ccxt (cryptocurrency exchange trading library which has support for a huge number of exchanges and APIs)





