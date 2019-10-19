### Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning   [Course Link](https://www.coursera.org/learn/introduction-tensorflow)

### Week two summary

- Ready to use datasets such as MNIST and Fashion MNIST has been discussed:
  - Image size: [28, 28] 
  - Image format: grayscale, mean 1 channel is present [28, 28, 1]
  - Fashion mnist includes 60,000 trainign images and 10,000 test images
  - Th whole dataset includes 70,000 samples.
  - There are 10 different lababels
  
- Relu function: It only returns x if x is greater than zero

- How to write a callback:

```
class myCallback(tf.keras.callbacks.Callback):
    def on_epoch_end(self, epoch, logs={}):
        if logs.get('accuracy') > 0.997:
            print("\the trainign reached 99% percent accuracy!")
            self.model.stop_training = True
.
.
.
callbacks = myCallback()
.
.
.
history = model.fit(x_train, y_train, epochs=10, callbacks=[callbacks])
print(history.epoch, history.history['accuracy'][-1])
```

- Link to lessons from the coursera week 1: 

    - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Course%201%20-%20Part%204%20-%20Lesson%202%20-%20Notebook.ipynb)
    - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Course%201%20-%20Part%204%20-%20Lesson%204%20-%20Notebook.ipynb)
    - [Optional Lesson ](https://rwoubqswsbrqgsewfxrtkb.coursera-apps.org/notebooks/week2/Exercise2-Question.ipynb)
    
Codes and more info at: https://colab.research.google.com/drive/1Vqw_WguUMt_BhMOi3l3cmcH4QRCN2Z7x
