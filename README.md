# Credit-Card-Fraud-Detector
First the dataset is obtained in the form of a csv file and the dataset is displayed.
There are 31 coloumns in the dataset : Time, V1-V28, amount and the class. The class signifies whether the tranasaction is fraud or not.
The Time and Amount coloumns have to be standardised to bring them to a same scale as V1-V28. Hence StandardScaler is used.
Then the shape of the dataset is found out- 284807 rows and 31 coloumns. The info regarding the dataset is also displayed, where all the columns are non-null.
As there are no null values in the attributes and there are no categorical values prersent, the dataset is not filled with median values and dummy variables are also not used.
The number of fraudulent and non fraudulent cases are found using value_counts().values[] and it is found that the number of fraudulent cases are very less in comparison to the non fraudulent cases. So the dataset is imbalanced, hence even if the dataset is trained using multiple algorithms, the result will be accurate as fraud cases are very less, which is not the correct method to predict the data present in the dataset.
Hence the dataset is divided into input features X and output labels y, and train and test sets are formed for evaluating and testing the models at a ratio of 80:20
To prevent imbalance of data, ADASYN oversampler is used and fed into the X_train and y_train sets
The correlation heat map is displayed to find out the relationship among the different attributes
Then the dataset is trained by evaluating the cross validation score using different models like SGD Classifier, Logistic Regression, Random Forest Classifier, Decision Tree Classifier, and XGB Classifier.
According to the cross validation scores, the Random Forest Classifier, Decision Classifier and the XGB Classifier performed well on training data
After evaluating the models, the test models are implemented using different models like SGD Classifier, Linear Regression, Logistic Regression, Random Forest Classifier, Decision Tree Classifier, and XGB Classifier.
The precison, recall, fi score and roc curves are found out for the different models.
The accuracy of the Random Forest Classifier, Decision Tree Classifier and the XGB Classifier are very high, with the XGB Classifier having the highest accuracy.
Whereas the precision of the Random Forest Classifier was the highest. The n_errors were also the least for the Random Forest Classifier.
Early Stopping(was trained until validation_0-auc hasn't improved in 20 rounds) was used to measure the AUC score from the roc curve for XGB CLassifier which was found out to be the highest.
Hence we can conclude that XGB Classifier has performed the best among all the models as it has the highest AUC score, whereas the Random Forest Classifier and the Decision Tree Classifier will also work well enough for this dataset.
