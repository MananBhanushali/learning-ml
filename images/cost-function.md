# Cost Function in Logistic Regression

## Why Squared Error Cost Function is not used

![Why Squared Error Cost Function is not used](../../images/squared-error-cost-fn-in-logistic-reg.png)

In Logistic Regression, the squared error cost function leads to a non-convex graph, which has multiple local minima. Running Gradient Descent on such a cost function would lead to different parameters depending on different starting points. Hence, Squared Error cost function is not used in logistic regression. 

>[!NOTE]
**The term inside the submission is called the loss.** In case of the squared error cost function, the loss is equal to (1/2)*(f-y)*2.
The mean of losses gives us the cost

## Logistic Loss function

![Logistic Loss Function](../../images/logistic-loss-function.png)

**y(i) is the true value ( actual result )**

When True Value is 1
![y(i) = 1](../.ii/images/../../../images/logistic-loss-1.png)

When True Value is 0
![y(i) = 0](../.ii/images/../../../images/logistic-loss-0.png)

>[Logistic Loss](../../labs/Course%201/Week%203/C1_W3_Lab04_LogisticLoss_Soln.ipynb)

## Simplified Cost Function

This Loss Function can also be written as:

![Simplified Cost Function](../../images/simplified-logistic-cost-function.png)

One of the terms in the simplified loss function will become 0 depending on whether y(i) is 0 or 1.

>[Cost Function in Logistic Regression](../../labs/Course%201/Week%203/C1_W3_Lab05_Cost_Function_Soln.ipynb)