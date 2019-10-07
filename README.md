# CAE_Shabnam
A model to perform classification using sci-kit

//ToDo : Test the model for validation set using k combinations to check if decision tree is overfitting or not.

First i have tried arranging and normalize the data
I have replaced the “empty/blank” options with the median of the specified column and then normalized the data to get it in range of -1 to 1,(used number-median/max-min)
I kept 20% of the data as test_set and trained my model on 80% of the data and tested on the test_set, for which the data is listed below.
Then i saw the correlation of the columns on each other,
The label column was more related to column 0, and also inversely related to 1 and 6
label    1.000000
0        0.181131
3        0.048308
2        0.041306
Id       0.025531
5        0.011474
9        0.006262
4        0.001026
7       -0.030878
8       -0.053851
1       -0.135486
6       -0.201772


So i used these 3 columns to run the classification task on 3 models: SVM,KNN, and decision tree.


With 0,1,6 column
KNN:
Accuracy = 0.890621354693211
[[43821  4081]
 [ 4358 24894]]
precision and recall: (0.9148052273391508, 0.9095456526702506)

Decision tree:30 depth
0.8560930087876195
[[43603  4299]
 [ 6804 22448]]
precision and recall: (0.9107344160995365, 0.8650116984573899)

SVM
linear
0.6379042187803772
[[15529  3495]
 [ 7680  4158]]
Rbf
0.6516103946600998
[[17786  1238]
 [ 9514  2324]]


With 0 to 9 column:
KNN:
0.9572284003421728
[[46030  1872]
 [ 1428 27824]]
precision and recall: (0.9609202120997036, 0.969910236419571)

Decision tree:30 depth:
0.97615159291806
[[47166   736]
 [ 1104 28148]]
precision and recall: (0.9842804058285667, 0.9768371765388361)

Decision tree performed really well on the data,F1 score was 98%.
Knn was also good, but SVM(linear and rbf) was not good.
So i used decision tree with depth 30 to run my final model.
