
### Convolutional Neural Networks in TensorFlow [Course Link](https://www.coursera.org/learn/convolutional-neural-networks-tensorflow/home/welcome)

### Week 1 Summary:  Exploring a Larger Dataset
- As it was discussed in the last course, using *ImageGenerator* and *flow_from_directory()*:
    - It could help you to load all of the trainig images automaticaly.
    - You could also, set the image preprocessing functionality for all of the loaded image, on-fly, such as shape, and normalization.
    - It also could label the images based on the directory name.
- To enable the *history* tracking of the accuracy and other performance factors, you can pass a history variable to model.fit or model.fit_generator during the training.

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

- To access mid-level feature maps and different layers of the model you can use, model.layers API.
- The validation accuracy is a better performance metric where we can track overfitting to trainign data, too.
- In general, overfitting is more likely to happen for the smaller datasets, since there is less likelihood of all pissible features being encountered in the training provess.  

- Summary of relation between filter, stride, channels/depths, and  input/output size in a convLayer:

```
Accepts a volume of size W1×H1×D1

Requires four hyperparameters:
 - Number of filters K,
 - their spatial extent F,
 - the stride S,
 - the amount of zero padding P.

Produces a volume of size W2×H2×D2 where:

W2=(W1−F+2P)/S+1
H2=(H1−F+2P)/S+1 (i.e. width and height are computed equally by symmetry)
D2=K

```
- Link to lessons from the coursera week 1:
  - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Course%202%20-%20Part%202%20-%20Lesson%202%20-%20Notebook.ipynb)
  - [Excersice](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Exercises/Exercise%205%20-%20Real%20World%20Scenarios/Exercise%205%20-%20Answer.ipynb)

Codes at: https://xxx
