# Fraudulent-Credit-Card-Transactions-Detection-Models-
In this project some machine learning models are trained for classifying some credit card transactions into two classes: fraud or not fraud. The dataset that is considered contains 1 million examples, but for computational needs only the first 10000 examples are used. Here you can find the complete dataset: https://www.kaggle.com/datasets/dhanushnarayananr/credit-card-fraud. 

The project is organized as follows: <br>

1. First of all a very simple EDA of the dataset is provided. <br>
2. After that some machine learning models are trained to predict if a transaction is fraudulent or not. Before that, a cross validation procedure is provided, thanks to RandomizedSearchCV, in order to tune the hyperparameters of all the considered models. These models are: <br>
* `K-Nearest Neighbors Classifier(KNN)` <br>
* `Decision Tree Classifier (DT)` <br>
* `Support Vector Classifier (SVC)` <br>
* `Random Forest Classifier(RF)`<br><br> 
3. In conclusion, the models are tested on the test set and the best model is choosen. 

Here it is a prospectus of the variables into the dataset:

|   VARIABLE NAME 	|   VARIABLE DESCRIPTION	|   VARIABLE TYPE	| VALUES  	|
|---	|---	|---	|---	|
|  distance_from_home 	|   the distance from home where the transaction happened.	|   continuous numerical	|   	|
|   distance_from_last_transaction	|   the distance from last transaction happened	|   continuous numerical	|   	|
|   ratio_to_median_purchase_price	|   Ratio of purchased price transaction to median purchase price	|  continuous numerical 	|   	|
|   repeat_retailer		|  Is the transaction happened from same retailer 	|  binary	|  1: yes <br> 0: no|
|   used_chip		|   Is the transaction through chip (credit card)	|   binary	|   1: yes <br> 0: no|
|   used_pin_number	|    Is the transaction happened by using PIN number	|   binary	| 1: yes <br> 0: no  	|
|   online_order		|   Is the transaction an online order	|   binary	|   1: yes <br> 0: no	|
|  fraud 	|   Is the transaction fraudulent	|   binary	|   1: yes <br> 0: no	|

# Conclusions

### In conclusion:

### 1) The best models to predict if a credit card transaction in fraudulent or not are Random Forest (RF) and Decision Tree (DT), since both have an accuracy of 99.9% and, more importantly, values of sensitivity and specificity nearly to 100%.

### 2) Choosing between them based on their performance is very hard, since the latter are essentially the same. 

### 3) The Random Forest indicates that the most important features for predicting if a transaction is fraudulent or not are: 'ratio_to_median_purchase_price', 'online_order' and 'distance_from_home'. This is in complete agreement with the EDA, and in particular with the correlation matrix analysis, indicates the same variables as the most relevant ones.
