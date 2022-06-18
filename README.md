# Fraudulent-Credit-Card-Transactions-Detection-Models-
In this project some machine learning models are trained for classifying some credit card transactions into two classes: fraud or not fraud. The dataset that is considered is pretty huge, since it contains 1 million examples, and it is also unbalanced, since the vast majority of the considered transactions are not a fraud. As we know when we have a binary classification problem and we are dealing with an unbalanced dataset the accuracy of the model is not a good metric.

Thus, for these reasons the project is organized as follows: <br>

1. First of all a very simple EDA of the dataset is provided. The latter is done on the entire dataset. <br>
2. After that a new dataset, called df_model, is defined. The latter contains the first 5000 non fraudulent transaction and the first 5000 fraudulent ones. In this way we work around both the computational problem, due to the gigantic dataset, and the imbalance problem. Then some machine learning models are trained on this df_model dataset to predict if a transaction is fraudulent or not. Before that, a cross validation procedure is provided, thanks to RandomizedSearchCV, in order to tune the hyperparameters of all the considered models. These models are: <br>
* `K-Nearest Neighbors Classifier(KNN)` <br>
* `Decision Tree Classifier (DT)` <br>
* `Support Vector Classifier (SVC)` <br>
* `Random Forest Classifier(RF)`<br><br> 
3. The models are tested on the test set and the best model is choosen. It results to be DT. 
4. A third dataset, called df_tot, is created. The latter is builded by adding some randomly selected data from the original dataframe, and it contains 2 millions examples, 1 million of fraudulent transaction and 1 million of not fraudulent ones. After that, the DT model, which gave us the best performance on df_model, is trained on the a train dataset builded starting from df_tot, and then the model is tested, showing an extremely high performance.  

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

### 1) The model that furnishes the best performance in forecasting if a transaction is fraudulent or not on the small balanced dataset is the Decision Tree (DT), with an accuracy of 99.85%. 

### 2) The Random Forest indicates that the most important features for predicting if a transaction is fraudulent or not are: 'ratio_to_median_purchase_price', 'online_order' and 'distance_from_home'. This is in complete agreement with the EDA, and in particular with the correlation matrix analysis, which indicates the same variables as the most relevant ones.

### 3) The Decision Tree also shows an extremely high performance on the gigantic balanced dataset, which is obtained by adding other randomly selected data to the original dataframe df, with an accuracy of 99.9995%.
