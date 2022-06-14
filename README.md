# btc-price-forecasting

## r/CryptoCurrency Daily Thread Sentiment

The following project is meant to be an introduction into data gathering, cleaning, and modeling with a Keras neural network. In a nutshell, we scrape comments from the r/CryptoCurrency subreddit's daily thread, label this data with Bitcoin's future price action, and attempt to predict future price action based on comment sentiment. This is a learning project, and should not be used in deployement.

Our data consists of a 2 dimensional matrix, where the columns store words, and the rows are comments from a specific daily thread. We use several Convolutional Neural Network (CNN) layers to filter out daily threads both horizontally (word-wise) and vertically (comment-wise) - importantly, this filtration is done seperately so as to prevent the spatial association of words in two different comments. With our data, this combination seems to perform better than a Recurrent Neural Network (RNN), Long Short-Term Memory (LSTM), as well as various combinations of [recurrent-type layers](https://keras.io/api/layers/recurrent_layers/).

The result of our model seems promising. For our test data, the model was able to predict Bitcoin's future price action (Bullish or Bearish) around 51% of the time. While this may not seem like much, it is better odds than a blind coin flip. Alone, it is not much of better odds, but if used in combination with other forecasting models the odds may increase.
