# Supervised Learning
1. K-Nearest Neightbors(KNN)
2. Bias-Variance Trade-Off
3. Cross-Validation
4. Lasso Regression
5. Ridge Regression
6. ROC and AUC

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
- How to measure model performance (accuracy)
- How to choose hyperparameter (K)

### 2. Bias-Variance Trade-Off
<img width="501" alt="Screenshot 2023-12-21 at 3 53 00 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/54207042-1ad5-4995-bd18-ae5f34ac8b73">
- We observe that as λ increases, the Bias2 increases, while the variance decreases. 
- The cause can be explained in different ways. For example, by adding the penalty, we are changing the optimizer of the ℓ2ℓ2 loss function. 
- This causes the bias, but has the benefit of making the objective function more convex. 
- Hence the solution is more stable, which reduces the variance. 
- The two trades-off and the sum display a U-shaped curve. 
- If we are asked to pick a λ value, we should pick the one that gives the smallest sum.

## 3. Cross Validation
- Cross-Validation is a resampling technique with the fundamental idea of splitting the dataset into 2 parts- training data and test data
-Train data is used to train the model and the unseen test data is used for prediction.

### We will compare two approaches: the k-fold cross-validation using cv.glmnet(), and the generalized cross-validation (GCV) using the lm.ridge() function.
#### lm.ridge() function
<img width="792" alt="Screenshot 2023-12-21 at 3 56 42 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/f8205a21-9389-4b58-8df1-c26d36a38bea">
<img width="725" alt="Screenshot 2023-12-21 at 3 56 50 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/8e346e2b-2368-4ab6-8106-3b5a2f45a63b">
- It shows that λ=15 is the best value. Now let’s write a cross-validation to calculate the corresponding error.

<img width="782" alt="Screenshot 2023-12-21 at 4 00 57 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/f71b088b-d817-4abb-a007-33e2ce1a323a">

#### glmnet package
<img width="713" alt="Screenshot 2023-12-21 at 4 01 05 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/fe4a294e-a8d8-4d9f-8d0a-a6c15af61b4a">
<img width="795" alt="Screenshot 2023-12-21 at 4 02 23 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/8bb69294-9242-4754-8d3e-65f0b642d45c">

- The two cross-validation best lambda values are quite different. This speaks about the problem of cross-validation’s instability when the number of observations is small. For example, if we perform the 5-fold cross-validation again, this may give us a completely different result:


### What are the benefits of L1 and L2?
- L2 regularization, also known as ridge regression, helps to prevent overfitting by penalizing large parameter values.
- On the other hand, L1 regularization, also known as Lasso regression, encourages sparsity in the model by setting some coefficients to zero, which can help with feature selection.

### L1 vs L2
### Ridge: It works well with multicollinearity.
- However, it never shrinks a coefficient to be zero and the final model will include all predictors, which is not good for feature reduction.

### Lasso: It helps with variable selection by shrinking parameter estimates to 0. 
- However, Lasso will suffer when two or more variables are strongly correlated. It only selects one of them randomly, which is not good for the interpretation of data.
- Lasso penalty is vulnerable to colinearity

## 4.Ridge Regression(L2 regularization)
- fuction = OLS + alpha * sum(parameter^2)

## 5.Lasso Regression(L1 regularization)
- fuction = OLS + alpha * sum(absolute_value(parameter))

## 6. ROC Curve with Logistic Regression
- logistic regression output is probabilities
- If probability is higher than 0.5 data is labeled 1(abnormal) else 0(normal)
- By default logistic regression threshold is 0.5
- ROC is receiver operationg characteristic. 
- In this curve x axis is false positive rate and y axis is true positive rate
- If the curve in plot is closer to left-top corner, test is more accurate.
<img width="714" alt="Screenshot 2023-12-21 at 3 50 33 PM" src="https://github.com/ColleenJung/Regularization-Regression/assets/119357849/84523e77-9a1e-450d-ad99-7b06cbb01500">
