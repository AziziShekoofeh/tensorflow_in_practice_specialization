### Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning   [Course Link](https://www.coursera.org/learn/introduction-tensorflow)

### Week four summary

- The role of ImageGenerator:
  - In many cases you need to generate the labels for images based on the folder structure and the name of the folder.
  - The folder structure requirment for *Autolabeling*:
```
Dataset Folder
└─── Train Data Folder
│   └─── Category One Folder (e.g. Lavender)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
│   └─── Category Two Folder (e.g. Sunflower)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
└─── Validation Data Folder
│   └─── Category One Folder (e.g. Lavender)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
│   └─── Category Two Folder (e.g. Sunflower)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
└─── Test Data Folder
│   └─── Category One Folder (e.g. Lavender)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
│   └─── Category Two Folder (e.g. Sunflower)
│       │   file1.jpg
│       │   file2.jpg
│       │   ...
```
  - At each time you need to point the ImageGenerator to the target directory (eg. Train, Validation, or Test Folder), to creater a *Feeder* for the dataset based on the batch size, image size (resize to the same size), and also class_mode. 
  - The name of *sub-directories* are the *labels* for the images inside that subdirectory. 
  - Class mode generate the labels basaed on your target problem needs, such as binary or multi category problem. 
  - ImageGenerator use *rescale* function for normalization of the data. 


Codes at: https://colab.research.google.com/drive/1LTYmtAqYaX53Idoa9h9C96PxalhmHfPk
