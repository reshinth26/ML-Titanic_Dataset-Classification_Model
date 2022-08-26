# ML-Titanic_Dataset-Classification_Model

Random Forest Classification model for predicting the survivors of Titanic shipwreck incident using 11 features dataset

The objective of this model was to predict which passengers will survive in the Titanic shipwreck.

I started by importing the data provided as a Pandas DataFrame, and then dropped the irrelevant features which were unique to all rows including PassengerId, Name, and Ticket No. as they will only generate noise and result in overfitting.

Then I checked how many of the remaining features had null values and found that three features, Age, Cabin, and Embarked had Null values. The feature Cabin had a lot of Null values and most of the filled values as unique, so I changed them to a categorical variable providing 0 for NULL values and 1 for the rest indicating whether they have been allotted a Cabin or not. For the Embarked column, which was a categorical variable and had about 2-3 NULL values, I filled those values with the mode of all the feature data. To replace NULL values of Age, if a person is in Cabin, I replaced the Age with the median of Cabin ages, if not in Cabin, then replaced with the median of non-cabin ages.

Then I changed the categorical variables like Sex and Embarked to numerical by creating dummies, and removing one of the dummy features to reduce the correlation of features.

Once done, I separated the training and test data for model training with 80% data for training. Then I scaled the data (except y variable) using the StandardScaler method, to equate the weightage of all the data available.

After fitting the Random Forest Classification model with the processed data, I achieved an accuracy of 0.81
