# Supervised Learning
1. K-Nearest Neightbors(KNN)
2. Cross-Validation
3. Lasso Regression
4. Ridge Regression
5. ROC and AUC

## 1.KNN
- KNN: Look at the K closest labeled data points
- fit(): fits the data, train the data.
- predict(): predicts the data
- k=3, means that Look at the 3 closest labeled data points

### Model complexity
- K is called a hyperparameter. For now just know K is hyperparameter and we need to choose it that gives best performace.
- small K can lead to overfit
- overfit means that model memorizes the train sets and cannot predict test set with good accuracy.
- large K can leant to underfit

### learned from KNN
- How to split data
- How to fit, predict data
- How to measure medel performance (accuracy)
- How to choose hyperparameter (K)

## 2. Cross Validation
- Cross-Validation is a resampling technique with the fundamental idea of splitting the dataset into 2 parts- training data and test data
-Train data is used to train the model and the unseen test data is used for prediction.

## 3.Ridge Regression
- Ridge regression(L2 regularization)
- fuction = OLS + alpha * sum(parameter^2)

## 4.Lasso Regression
- Lasso regression(L1 regularization)
- fuction = OLS + alpha * sum(absolute_value(parameter))

## 5. ROC Curve with Logistic Regression
- logistic regression output is probabilities
- If probability is higher than 0.5 data is labeled 1(abnormal) else 0(normal)
- By default logistic regression threshold is 0.5
- ROC is receiver operationg characteristic. 
- In this curve x axis is false positive rate and y axis is true positive rate
- If the curve in plot is closer to left-top corner, test is more accurate.
