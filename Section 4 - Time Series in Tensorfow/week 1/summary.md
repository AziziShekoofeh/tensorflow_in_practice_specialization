
### Sequences, Time Series and Prediction in TensorFlow [Course Link](https://www.coursera.org/learn/tensorflow-sequences-time-series-and-prediction/home/welcome)

### Week 1 Summary:  Sequences and Prediction

- Time series: ordered sequence of values that are `usually' equally spaced over time. For example stock prices, weather forcasts, historical trends such as Moore's law:
	- Univariate Time Series: Single value per time steps. e.g. hour by hour temperature
	- Multivariate Time Series: Multiple value per time steps. e.g. hour by hour weather
	
- Multivariate time series is helpful to undertand the impact of the related data and to see correlation between different series and trend.

- Time seriess application with machine learning:
	- Prediction of forecasting based on the data
	- Imputation: projection of unknown or missing data. i.e. projecting back in time which means to have an estimate of the data properties and trends before started time of the collection or to fill-in the holes and missed data point that they are not exist. 
	- Detection of the anomalies, for example server attacks.
	- Determination of the patterns, like speech recognition. 
 
- Seasonality: A regular change in shape of the data and when patterns repeat at predictable intervals. For example, peak of users in a website or shopping center at certain time periods.

- Trend: An overall direction for data and when time series have an specific direction that moving in, like upwards or downwards.

- Noise: Unpredictable changes in time series data

- Autocorrelation and autocorrelated time series: 
	- The time series is created with the delayd or lagged copy of the time series data itself plus some spike, so we can see determenstic behavior along some random spikes. 
	- Autocorreleted time series have memories, and eacch steps depend on the previous ones. 
	- Spike and random values which cannot predict based on past values also called `Innovation'.
	- It also could be multiple lagged copies or autocorrelation. 
	- Data will follow a predictable shape with different scales.
	
```
v(t)  = alpha * v(t-1) + betha * v(t-100) + random noise
```

- Seasonality, autocorreletaion and trend can happen together for some of the time series.

```
Seasonality + Trend + Autocorrelation + Noise
```

- Non-stationary time series: when we have a big event or massive change into normal behaviour of the time series happens which can break trend and seasonality.

- For non-stationary time serie sometimes it is better to train our models after the non-stationary point and big event time steps.

 - How to use the time series with data-driven approaches:
	- Fixed partitioning: Training period, validation period, test period.
	- Roll-Forward Partitioning: Gradually increasing the training period by short periods, like a few time steps. 

 - Some technical point on partioning: 	
	- In partitioning we have to account for seasonality and contain atleast one season in each partition. 
	- The final optimal model should be also trained on the fixed test period, because it is the best representative period. So, you may also consider a test period in future and partition all the current data into train and validation. 

 - Metrics: Errors = Forcasts - Actual
 
 ```
 errors = forcasts - actual
 mse = np.square(errors).mean()   # mean square error
 rmse = np.sqrt(mse)              # root mean square error
 mae =  np.abs(errors).mean()     # mean absolute error/deviation
 mape = np.abs(errors/x_valid).mean() # mean absolute percentage error
 ```
 
 - To access metrics you can use *keras.metrics*.
 - Choice of metrics technical consideration: if large errors are potentially dangerous and they cost you much more than smaller errors, then you may prefer the mse. But if your gain or your loss is just proportional to the size of the error, then the mae may be better. 
 
- Statistical Forecasting:
	- Naive forecasting: Assume that the previous value will be the current step value.
	 - Moving Average: A common and very simple forecasting method is to calculate a moving average. 
	 
	 
 - Differencing: Removing of seasonality and trend out of the time series. So instead of studying the time series itself, we study the difference between the value at time T and the value at an earlier period. This period is the lenght of your season.
 
 - We can smooth the prediction and noise by removig the moving average of the noise in the past and present values. [needs re-state!]
 
 Link to course notebooks:
 
 - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP_Week_1_Lesson_2.ipynb)
 
 - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%201%20-%20Lesson%203%20-%20Notebook.ipynb)
 
Codes at: https://colab.research.google.com/drive/xxxx