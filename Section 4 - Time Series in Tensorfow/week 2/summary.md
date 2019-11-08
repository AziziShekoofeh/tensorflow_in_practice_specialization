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
    
- Sequence bias is when the order of things can impact the selection of things. To avoid sequence bias we need to shuffle it. [Q: why? sometimes bias and orders are important!]

Codes at: https://colab.research.google.com/drive/xxxx
