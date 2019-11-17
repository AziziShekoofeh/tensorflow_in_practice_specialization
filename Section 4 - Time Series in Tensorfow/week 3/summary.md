### Sequences, Time Series and Prediction in TensorFlow [Course Link](https://www.coursera.org/learn/tensorflow-sequences-time-series-and-prediction/home/welcome)

### Week 3 Summary:  Recurrent Neural Networks for Time Series


- RNNs are contain recurrent layers, they are designed to analysed text, time-series or any other series and sequences.
  - Input shape of a layer of RNN is 3 dimensional : [batch_size, #time-steps, #data-dimensions]
  - Vinalla RNNs have a memory cells and could generate hidden states to pass to next step and also an output at the current time-step.
  - State for the step-0 is 0 or a random number. 
  - Output shape at *each time step* is : [batch size, **#units**, #data-dminsion]
  - Hidden state shape is also have similar shape to the output.
- Seqence-to-Vector RNN will ignore all of the output expect the last time step one. This is the default behaviour of the TF. If you want to connect multiple layers of RNN you should set the *return_sequence* flag as True to pass all of the outputs to the next layer. 


- Defining a Vanillar/Simple RNN in TF:.
  - *None* means RNN should be able to handle sequence of different lenght.
  - If we set *return_sequences* True for the second layer RNN will return all of the time steps output.
  - TF/Keras will handle this by repeating Dense layer structure for all of the layers, hoever, sometimes it will cause some error and dimensionality missmatch.

```
model = tf.keras.models.Sequential([
    tf.keras.layers.SimpleRNN(window_size, input_shape=[None, 1], return_sequences=Ture), 
    tf.keras.layers.SimpleRNN(window_size), 
    tf.keras.layers.Dense(1)
])
```

- Lambda Layer: works simillar to lambda function in python, and expand the functionality of TensorFlow's kares. It allows you to execute arbitrary code while training. For example:
  - To increase dimentionally of the data as RNNs input.
  - Handling Hypernolic Tanh data range output [1, -1] by multiplying it by 100.0 which makes learning process easier.
  
```
model = tf.keras.models.Sequential([
    tf.keras.layers.Lambda(lambda x: tf.expand_dims(x, axis=-1), input_shape=[None]),
    tf.keras.layers.SimpleRNN(window_size, return_sequences=True), 
    tf.keras.layers.SimpleRNN(window_size), 
    tf.keras.layers.Dense(1),
    tf.keras.layers.Lambda(lambda x: x* 100.0)
])
```

- Huber Loss: is a loss function for robust regression and it is less sensitive to the noise.([Reed More](https://en.wikipedia.org/wiki/Huber_loss))

- LSTMs: to deal with the vanishing of the information in long sequences, LSTM uses cell states in addition ot the hidden state to improve the performance of sequence analysis. So, the data from very early steps can have better impact on far away steps and overall network. Cell states can also be bidirectional so the previous cells and steps will effect the earlier steps. You cna define a LSTM as follow:

```
model = tf.keras.models.Sequential([
  tf.keras.layers.Lambda(lambda x: tf.expand_dims(x, axis=-1),
                      input_shape=[None]),
    tf.keras.layers.Bidirectional(tf.keras.layers.LSTM(10, return_sequences=True)),
  tf.keras.layers.Bidirectional(tf.keras.layers.LSTM(10)),
  tf.keras.layers.Dense(1),
  tf.keras.layers.Lambda(lambda x: x * 100.0)
])
```

- Note: use *tf.keras.backend.clear_session()* to clear internal variables and model parameters from previous experiments. 


 Link to course notebooks:
 
 - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%203%20Lesson%202%20-%20RNN.ipynb#scrollTo=5He3pp-Hj758)
 
 - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%203%20Lesson%204%20-%20LSTM.ipynb)
 
  - [Exercise](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%203%20Exercise%20Answer.ipynb)



Codes at: 

- [Part 1](https://colab.research.google.com/drive/1RaCsJlHlvHbI5auZPnGDnvl9FHXZi-od)
- [Part 2](https://colab.research.google.com/drive/1tbYmFvbcDs0Hj9z2Ei3BkCBSE6bkn7Dg)
- [Excersise Answer](https://colab.research.google.com/drive/1-QdNEZ0ZnsBFKfUfc6mATBuLgcs2SLcy)
