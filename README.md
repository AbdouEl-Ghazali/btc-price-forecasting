# btc-price-forecasting

## CryptoCurrencySentiment (r/CryptoCurrency Daily Thread Sentiment)

The following project is meant to be an introduction into data gathering, cleaning, and modeling with a Keras neural network. In a nutshell, we scrape comments from the r/CryptoCurrency subreddit's daily thread, label this data with Bitcoin's future price action, and attempt to predict future price action based on comment sentiment. This is a learning project, and should not be used in production.

Our data consists of a 2 dimensional matrix, where the columns store words, and the rows are comments from a specific daily thread. We use several Convolutional Neural Network (CNN) layers to filter out daily threads both horizontally (word-wise) and vertically (comment-wise) - importantly, this filtration is done seperately so as to prevent the spatial association of words in two different comments. With our data, this combination seems to perform better than a Recurrent Neural Network (RNN), Long Short-Term Memory (LSTM), as well as various combinations of [recurrent-type layers](https://keras.io/api/layers/recurrent_layers/).

The result of our model seems promising. For our test data, the model was able to predict Bitcoin's future price action (Bullish or Bearish) around 51% of the time. While this may not seem like much, it is better odds than a blind coin flip. Alone, it is not much of better odds, but if used in combination with other forecasting models the odds may increase.

## BTCPrice

Recurrent Neural Network (RNN) architectures such as Long Short-Term Memory (LSTM) can
be useful in time series forecasting. LSTM, when compared to other neural network architectures,
improves a model’s ability to remember special events that may influence future outcomes. This
can be useful for time series with unknown delays between event occurences and their outcomes.

One possible usecase for LSTM is Bitcoin price forecasting. Technical analysis is commonly used
for trading and/or investing in Bitcoin. The general notion is that recent price action can be used
to forecast the price of Bitcoin in the near future. In greater detail, special chart formations are said
to be useful in predicting future price action. This project aims to explore that idea at an abstract
level. Using basic technical indicators such as the simple and the exponential moving averages for
price, as well as for volume, we hope to see a correlation between Bitcoin’s past and near future
price action. That is to say, a successful prediction will take the 50 most recent hours of indicator
data, and predict the next 1 hour of Bitcoin’s price.

This project takes basic technical indicators for Bitcoin such as price, volume, trade count, and several moving averages (simple and exponential), and creates an LSTM model that can predict hourly price action with 82% accuracy. *DISCLAIMER: It is important to note that this accuracy figure is based off of bullish or bearish price action only. This project should not be used in the Bitcoin market, as it is intended for learning purposes.*
