**********IMPLEMENTAI- HACKATHON 28-29 Sept 2019 by McGill***********

> Attempting problem proposed by CAE:

Problem : CAE has collected data during the training session of pilots and their responses of being flagged or not. Based on pre-labelled data, we train a model to flag pilot accurately on future training sessions of pilot.

Steps involved: 

- We are presented with data from CAE

- After loading the dataset given by CAE:
1. Replacing the “empty/blank” options with the median of the specified column
2. Normalizing the data to get it in range of -1 to 1
3. There is no categorical data.

- For cross validation purpose:
1. Goingt to keep 20% of the data as test_set and train my model on 80% of the data.

- Try to get the relation between input and output, which input is more effecting the output. To do so, 
1. Calculating the correlation of the columns with respect to label,
2. The correlation data is given below:

![Test Image 1](https://github.com/shabnm/CAE_Shabnam/blob/master/correlation.PNG)

3. As depicted, the label is more related to column 0, 1 and 6.
4. Directly related to 0 and inversely related to 1 and 6.


- So I am using 3 columns(0,1,6) to run the classification task on 3 models:
1. SVM,
2. KNN, and 
3. decision tree.

- Results:

**With 0,1,6 column**

**KNN**:<br/>

Accuracy = 0.890621354693211<br/>
[[43821  4081]<br/>
 [ 4358 24894]]<br/>
precision and recall: (0.9148052273391508, 0.9095456526702506)<br/>

**Decision tree**:30 depth<br/><br/>
0.8560930087876195<br/>
[[43603  4299]<br/>
 [ 6804 22448]]<br/><br/>
precision and recall: (0.9107344160995365, 0.8650116984573899)<br/>

**SVM**<br/>
*linear*<br/>
0.6379042187803772<br/>
[[15529  3495]<br/>
 [ 7680  4158]]<br/>
 
*Rbf*<br/>
0.6516103946600998<br/><br/>
[[17786  1238]<br/>
 [ 9514  2324]]<br/>


**With all columns**:<br/>
**KNN**:<br/>
0.9572284003421728<br/>
[[46030  1872]<br/>
 [ 1428 27824]]<br/>
precision and recall: (0.9609202120997036, 0.969910236419571)<br/>

**Decision tree**:30 depth:<br/>
0.97615159291806<br/>
[[47166   736]<br/>
 [ 1104 28148]]<br/><br/>
precision and recall: (0.9842804058285667, 0.9768371765388361)<br/>

Decision tree performed really well on the data,F1 score was 98%.
Knn was also good, but SVM(linear and rbf) was not good.
So i used decision tree with depth 30 to run my final model.
