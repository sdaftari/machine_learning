Sentiment Classification using a Recurrent Neural Network

In this notebook, I am using a Recurrent Neural Network to classify sentiments of a IMDB movie reviews into positive and negative. The RNN based solution gives more accurate results than a simple neural network that uses 
positive-negative ratio of each word as features. This is because the RNN not only considers the current word, but also takes into consideration the sequence of words, which helps to predict the next word more accurately. 
I am using LSTM cells which contain the information about the past words used and predict the sentiment as positive or negative based on that information.

Topics Covered:
* Sentiment Analysis
* RNN
