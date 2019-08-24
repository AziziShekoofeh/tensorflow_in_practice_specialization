## Week Four summary

- The role of ImageGenerator:
  - In many cases you need to generate the labels for images based on the folder structure and the name of the folder.
  - The folder structure is as follow:
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
  - machine learning: input:answers (labels), data -> output: rules [learning an unknown patterns and functionality]
  
- Dense: a layer of unconnected neurons, which will be connected to the next layer nodes [course wrongly mentioned a layer of connected node!]

- Loss function: function to be use to measure how good is the prediction.
- Optimizer: Will generate a new and improved guess based on the current guess and prediction
- Convergence: Is the process of getting closer to the correct predictive function
- Fitting: is the process of training, which tries to fit the set of inputs to targets.

Codes at: https://colab.research.google.com/drive/1GXHm-ICWyFYqRl3F5B-dRjwUZpDKgAk7
