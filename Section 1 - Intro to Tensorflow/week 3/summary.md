### Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning   [Course Link](https://www.coursera.org/learn/introduction-tensorflow)

### Week three summary

- Recommended course and notes to fully undertand Convolutional Neural Networks (CNNs): [Stanford CS231n](http://cs231n.github.io/convolutional-networks/)

- **Convolution**:  is a technique to filter or isolate the features inside an image. In mathematics (in particular, functional analysis) convolution is a mathematical operation on two functions (f and g) that produces a third function expressing how the shape of one is modified by the other ([Wikipedia](https://en.wikipedia.org/wiki/Convolution)). 

- In neural network, you can apply concolution to extract high-level features from an image, using filters/kernels. Using this technique, and by isolation of the features, decision making will get easier, and we can get an improved image recognition.

- **Pooling**: is a technique to reduce the information in an image while maintaining features. Ususally, pooling is being used to reduce the dimensions, and correspondingly, the number of learnable parameters in the neural network [[Link](http://cs231n.github.io/convolutional-networks/#pool)]. 

- To define the pooling and convolutional layer in Tensorflow, you can use:

```
keras.layers.Conv2D(filters=c, kernel_size=(f,f), activation='relu', input_shape=image_size)
keras.layers.MaxPooling2D(pool_size=(2,2))
```
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

- Last words: Design of the CNNs is important, and poor design could even degrade the performance in comarison to a plain DNN. 

- Link to lessons from the coursera week 1: 

    - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Course%201%20-%20Part%206%20-%20Lesson%202%20-%20Notebook.ipynb)
    - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Course%201%20-%20Part%206%20-%20Lesson%203%20-%20Notebook.ipynb)
    - [Optional Exercise](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/Exercises/Exercise%203%20-%20Convolutions/Exercise%203%20-%20Question.ipynb)
    
    
codes at: https://colab.research.google.com/drive/1E94MtSXiOgbe5PQMe5KKDh8GBPA-Y7v9


