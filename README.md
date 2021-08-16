
#Predicting the cause of bushfires in the summer of 2019-2020 #

This project is currently predicting the cause of bushfire's in the summer of 2019-2020. Four reasons are leading to the bushfires: accident, burning off, lightning, and arson. I have selected boosted tree method for the model.  



**Data pre-processing steps **

There is a disparity in the month column for the training and prediction set in the given data set. I have filtered the month column of the training data set to like it in the prediction set. The histogram of the dist_road variable shows a positively skewed distribution where i have applied a log transformation to reduce the skewness. Also, when you look at the classes in the data set, you can see that it is a very imbalanced data set that needs to be assigned with weights to predict the classes accurately. For example, 'burning off' is the class with the lowest proportion in the data set that needs to be assigned with the highest weights. In addition, the boxplots of each variable helped to identify the outlier in the data set. Besides, I have used the k nearest neighbour method(k=5) to impute the missing values in the data set.



**Important variables for the prediction**

As a part of variable selection, I have passed all the variables, which i thought will help the model predict the classes accurately. Then I used the 'xgbimportance' function to look at the variable importance of the model, which helped me identify the variables with the highest priority. Then I have picked the variables with the highest gain value to try in the model. 


**Model performance **

I have used xgboost engine to predict the model. The cross-validation helped the model to try a different set of training and test data. After trying other model parameters, the model has chosen the number of variables randomly selected for the split(mtry) as 9, the number of trees as 400 and the depth of the tree as 7 to fit the best model. The model with the highest roc value has chosen as the best model.

