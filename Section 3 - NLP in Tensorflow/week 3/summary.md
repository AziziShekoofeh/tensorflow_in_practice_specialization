### Natural Language Processing in TensorFlow  [Course Link](https://www.coursera.org/learn/natural-language-processing-tensorflow)

### Week three summary

- Motivation: The context of words is hard to follow when they are broken down into sub-words and "sequence" in which the tokens of the sub-words appears, it is really important to understand the meaning. Until now, we just looked at the non sequencial networks, but we need specialized networks to also handle sequences, and relationship between different steps. So, we need inherent sequencing! 

- Recurrent Neural Networks (RNNs): Special kind of the neural networks taht considered the sequenctional and temporal relationships. So instead of *f(data, label) = rule*, we also have a temporal relation, and we consider previous output as the input to the current time steps. 

- RNNs have different types including: LSTM, GRU, and Convolutional RNNs

- LSTM will help to pass the relevent context from earlier steps, to the later steps using the *cell state*. Also, cell state could be bi-dirctional so the context from later steps can impact the earlier steps/context. 

- Be advised that if you have a multilayer LSTM module in Keras you should set the *return sequences* to True, so we insure the output of the LSTM match the desired inputs of the next one.

```
tf.Keras.Layers.Bidirectional(tf.keras.layers.LSTM(n1, return_sequences=True))
tf.Keras.Layers.Bidirectional(tf.keras.layers.LSTM(n2))

```
- Some Notes:
    - For analysis of the text sequences, yo also have the option to use the 1D convolutional neural network. 
    - Accuracy and Loss for multilayer LSTMs are more smooth, specially in the long term training.
    - Due to the nature of NLP, and out of vocabulary words, we are always prone to overfitting, because these words cannot be classified during validation.

- Link to lessons from the coursera week 2: 

    - [IMDB Subwords 8K with Single Layer LSTM](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%201a.ipynb)
    - [IMDB Subwords 8K with Multi Layer LSTM](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%201b.ipynb)
    - [IMDB Subwords 8K with 1D Convolutional Layer](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%201c.ipynb)
    
     - [Sarcasm with Bidirectional LSTM](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%202.ipynb#scrollTo=g9DC6dmLF8DC)
    - [Sarcasm with 1D Convolutional Layer](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%202c.ipynb#scrollTo=g9DC6dmLF8DC)
    - [IMDB Reviews with GRU (and optional LSTM and Conv1D)](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%203%20-%20Lesson%202d.ipynb#scrollTo=nHGYuU4jPYaj)
    
Codes at: https://colab.research.google.com/drive/xxxx
