#  Classification on Colab using MNIST dataset


**DESCRIPTION**

1. MNIST dataset, which is a set of 70,000 small images of digits
handwritten by high school students and employees of the US Census Bureau.
Each image is labeled with the digit it represents.
This set is called the “hello world” of Machine Learning:
Whenever people come up with a new classification algorithm they are curious to see how it will perform on MNIST.

2. Scikit-Learn provides many helper functions to download popular datasets. MNIST is one of them.

    >>> from sklearn.datasets import fetch_openml
    
    >>> mnist = fetch_openml('mnist_784', version=1)
    
    >>> mnist.keys()
    
dict_keys(['data', 'target', 'feature_names', 'DESCR', 'details',
               'categories', 'url'])

3. Let’s look at these arrays:

    >>> X, y = mnist["data"], mnist["target"]
    
    >>> X.shape
     
    (70000, 784)
    
    >>> y.shape
   
    (70000,)
    
    
Note:
  Datasets loaded by Scikit-Learn generally have a similar dictionary   structure, including the following:
  
      A DESCR key describing the dataset
      
      A data key containing an array with one row per instance and one column per feature
      
      A target key containing an array with the labels
      
4. Let’s take a peek at one digit from the dataset.

        import matplotlib as mpl

        import matplotlib.pyplot as plt

        some_digit = X[0]

        some_digit_image = some_digit.reshape(28, 28)

        plt.imshow(some_digit_image, cmap="binary")

        plt.axis("off")

        plt.show()

        mls2 03in01


Note:

  There are 70,000 images in MNIST, and each image has 784 features.
  
    This is because each image is 28 × 28 pixels, and each feature simply represents one pixel’s intensity, from 0 (white) to 255 (black).
    
    This looks like a 5, and indeed that’s what the label tells us:

>>> y[0]

'5'
    
6. Note that the label is a string. Most ML algorithms expect numbers, so let’s cast y to integer:

>>> import numpy as np

>>> y = y.astype(np.uint8)


A few more images from the MNIST dataset.

<img width="600" alt="Maze" src="https://user-images.githubusercontent.com/109574120/216806352-5420be15-b78f-4a56-a867-07004026baed.png">

The MNIST dataset is actually already split into a training set (the first 60,000 images) and a test set (the last 10,000 images):

    X_train, X_test, y_train, y_test = X[:60000], X[60000:], y[:60000], y[60000:]
    
Note:

    The training set is already shuffled for us, which is good because this guarantees that all cross-validation folds will be similar (you don’t want one fold to be missing some digits).
    
    Moreover, some learning algorithms are sensitive to the order of the training instances, and they perform poorly if they get many similar instances in a row.
Shuffling the dataset ensures that this won’t happen.
