### Sequences, Time Series and Prediction in TensorFlow [Course Link](https://www.coursera.org/learn/tensorflow-sequences-time-series-and-prediction/home/welcome)

### Week 4 Summary:  Real-world Time Series Data

- To improve th eperformance, instead of the Lambda layer to reshape our input firstly, we can use a Conv-1D to learn representative filters on the input series:

```
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv1D(filters=32, kernel_size=5, strides=1, padding="casual", activation="relu", input_shape=[None, 1]),
    tf.keras.layers.SimpleRNN(window_size, return_sequences=True), 
    tf.keras.layers.SimpleRNN(window_size), 
    tf.keras.layers.Dense(1),
    tf.keras.layers.Lambda(lambda x: x* 100.0)
])
```
- One reason for small spike and noisy behaviour of the learning curve could be the small batch size which introduce further randome noise. 

- MAE is a better analytic for measuring accuracy of predictions for time series and sequences because it won't heavily punish larger error like MSE.

- The experiments are showing to be able to have a good prediction for time series, we need a combination of CNN, RNNs, and also DNN. 


 Link to course notebooks:
 
 - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%204%20Lesson%201.ipynb)
 
 - [Lesson 2.1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%204%20Lesson%205.ipynb)
 
 - [Lesson 2.2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%204%20Lesson%203.ipynb)
 
  - [Exercise](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%204%20Exercise%20Question.ipynb)

  - [Exercise Answer](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%204%20Exercise%20Answer.ipynb)

Codes at: 

- [Part 1](https://colab.research.google.com/drive/xxx)
- [Part 2](https://colab.research.google.com/drive/xxx)
- [Excersise Answer](https://colab.research.google.com/drive/xxx)
