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

## What are the benefits of L1 and L2?
- L2 regularization, also known as ridge regression, helps to prevent overfitting by penalizing large parameter values.
- On the other hand, L1 regularization, also known as Lasso regression, encourages sparsity in the model by setting some coefficients to zero, which can help with feature selection.

## L1 vs L2
# Ridge: It works well with multicollinearity.
- However, it never shrinks a coefficient to be zero and the final model will include all predictors, which is not good for feature reduction.

# Lasso: It helps with variable selection by shrinking parameter estimates to 0. 
- However, Lasso will suffer when two or more variables are strongly correlated. It only selects one of them randomly, which is not good for the interpretation of data.
- Lasso penalty is vulnerable to colinearity

## 3.Ridge Regression(L2 regularization)
- fuction = OLS + alpha * sum(parameter^2)

## 4.Lasso Regression(L1 regularization)
- fuction = OLS + alpha * sum(absolute_value(parameter))

## 5. ROC Curve with Logistic Regression
- logistic regression output is probabilities
- If probability is higher than 0.5 data is labeled 1(abnormal) else 0(normal)
- By default logistic regression threshold is 0.5
- ROC is receiver operationg characteristic. 
- In this curve x axis is false positive rate and y axis is true positive rate
- If the curve in plot is closer to left-top corner, test is more accurate.
