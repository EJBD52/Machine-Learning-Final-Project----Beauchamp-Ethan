# Final Analysis

## Distribution of classes

![download](https://user-images.githubusercontent.com/104394105/167068870-ef378a14-cec3-4b77-b0ab-82d155d41a6c.png)
* The target column is "stroke" and the dataset is very imbalanced, there are 4861 rows of stroke = 0, but only 249 rows of stroke = 1.
* To achieve a high accuracy classification model, we need to resolve this dataset imbalance issue using oversampling or undersampling methods.

## Missing Values Imputation
* There are 201 rows that have missing values in the "bmi" column. 
  >* Among them, there are 40 rows that "stroke" is 1. This means they shouldn't be dropped because of the imbalanced nature of the dataset.
  >* Therefore, missing values imputation should be used for these missing values.

## Analysis for non-numerical columns
* The "id" is only the identifier of the rows, so it should be dropped before apply Modeing.
* Other categorical features like ('gender', 'ever_married', 'work_type', 'Residence_type', 'smoking_status') should be kept for classification.

## Encoding for Categorical features
* Since the number of unique values for all categorical columns are less than 5, and the dataset does't have many features, all features can be one-hot encoded.

## Oversampling for Data Balancing
* Because of how imbalanced the dataset is, data should be oversampled.
  >* This results in an oversampled dataset of 9722 rows including 4861 stroke: yes cases and 4861 stroke: no cases.
  >* Overall classification accuracy can be imporved by using this oversampling method.

## Analysis for the relationship between accuracy and percent of training data.
![download](https://user-images.githubusercontent.com/104394105/167069431-64b1f261-e9db-4d24-93fc-222ff2065c93.png)
* From the above plot, we can see that the decision tree classifier is better than logistic regression classifier for every split rate.
* The Decision Tree classifier has the best accuracy for split rate = 0.1, while Train : Test = 90% : 10%, so accuracy is maximized.

## Visualization for Decision Tree Classifier
![download](https://user-images.githubusercontent.com/104394105/167069499-567f07d4-8190-4a5f-82bb-ec476a11a17b.png)

![download](https://user-images.githubusercontent.com/104394105/167069511-6752a80e-a2a2-432b-b256-597a84c4a75f.png)

##### Conclusion
* From the above visualization of the Decision Tree classifier, we can check the performances and feature importances for this model.
* It appears that less than 20 cases were incorrectly predicted as "stroke" : yes, while all other cases were predicted correctly.
  >* The test accuracy was over 97% for 973 test cases.
* It is easy to identify feature importances such as "age", "avg_glucose_level", "bmi" , and "smoke" are the important features related to the stroke column.
  >* From the text representaion and feature importance bar plot, it appears age is the main factor of stroke.
* Overall, the Decision Tree is better than Logistic Regression classifier
  >* First, the accuracy of the Decision Tree is higher than the test accuracy of Logistic Regression classifier.
  >* Resulting test accuracy of the Decision Tree is over 97%, but the test accuracy of Logistic regression is less than 80%.
  >* Second, from the accuracy line plot, it's apparent that the decision tree classifier is better than the logistic regression classifier for every split rate. 
  >* The Decision Tree classifier has the best accuracy for split rate = 0.1, while Train : Test = 90% : 10%, accuracy is maximized.
