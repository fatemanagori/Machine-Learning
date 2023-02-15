# KNN + Confusion Matrix + IRIS Data set + Colab

In Machine Learning world model performance is everything. There are several metrics using which we will be able to evaluate our model.

Confusion matrix is one such important tool which helps us evaluate our model’s performance. As the name suggests it is a matrix of size n x n .where ’n’ is the number of class labels in our problem.

Now, let’s take a look at confusion matrix structure. Here,I am showing the python standard matrix notation for two class classification.

<img width="600" alt="Maze" src="https://user-images.githubusercontent.com/109574120/218939725-9cbca6fd-da19-4891-90b1-097d1f0588df.png">

In Python’s implementation of confusion matrix, rows show actual values and columns indicate predicted values. Given below is the description of each cell.

    TP (True Positives):

Actual positives in the data, which have been correctly predicted as positive by our model. Hence True Positive.

    TN (True Negatives):

Actual Negatives in the data, which have been correctly predicted as negative by our model. Hence True negative.

    FP (False Positives):

Actual Negatives in data, but our model has predicted them as Positive. Hence False Positive.

    FN (False Negatives):

Actual Positives in data, but our model has predicted them as Negative. Hence False Negative.


In ML, We have so many metrics. Out of which most known and used one is Accuracy.

Accuracy:

<img width="600" alt="Maze" src="https://user-images.githubusercontent.com/109574120/218940175-7074240f-8b2b-49a8-bd99-e77a345e57d3.png">

iPython note book can be found [HERE](https://github.com/fatemanagori/Machine-Learning/blob/main/Supervised%20Learning/KNN%20%2B%20Confusion%20Matrix%20%2B%20Iris%20Data%20set%20%2B%20Colab/knn_iris.pdf)

