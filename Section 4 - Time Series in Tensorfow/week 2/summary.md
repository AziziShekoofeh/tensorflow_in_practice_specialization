### Sequences, Time Series and Prediction in TensorFlow [Course Link](https://www.coursera.org/learn/tensorflow-sequences-time-series-and-prediction/home/welcome)

### Week 2 Summary:  Deep Neural Networks for Time Series

- Features in time-series: a number of values in the series, or the value associated with each time steps in the traget window.
- Labels in time-series: the next value in the time-serie rigth after our traget window.
- We can us *tf.data.Dataset.range()* to create a datatset of timeseries. 
    - Using *window()* method and *shift* flag, we can set our desire properties for the value of shift and target window. 
    - We also can use *drop_reminder=True* to get the same size windows by truncating the remainders. 
    - *shuffle()* method can be use to shuffle the data before training.
    - *numpy()* method can change the time series created to the numpy list usable for machine learning.
    - *map()* and *flat_map()* are also usefull to get the features (window[:-1]) and the last item (window[-1:]) as label.
    - *batch()* method can be use to create training batch. 
    
```
dataset  = dataset.map(lambda window: (window[:-1], window[-1:]))
```

- To set the validation and training data with some specific split time:

```
time_train = time[:split_time]
x_train = series[:split_time]
time_valid = time[split_time:]
x_valid = series[split_time:]
```

- Windowed dataset: A fixed subset of a time series. [Very confusing!]
- Sequence bias is when the order of things can impact the selection of things. To avoid sequence bias we need to shuffle it. [Q: why? sometimes bias and orders are important!]

- To inspect the values of the learned parameters in a layer after training we need to assign a variable to our target layer, and inspect the properties after training.

- To set the learning rate of the SGD optimizer you can use *lr* flag property! 

- To change the learning rate of an optimizer on the fly you can use the callback function, ue LearningRateScheduler in the callback name space, and assign that to the callback. 

 Link to course notebooks:
 
 - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%202%20Lesson%201.ipynb#scrollTo=Lrv_ghSt1lgQ)
 
 - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%202%20Lesson%202.ipynb#scrollTo=ou-WmE2AXu6B)
 
  - [Lesson 3](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%202%20Lesson%203.ipynb#scrollTo=efhco2rYyIFF)



Codes at: https://colab.research.google.com/drive/xxxx
