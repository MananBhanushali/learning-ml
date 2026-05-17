# Multiple Linear Regression and Vectorization

![Multple Features Notation](../../images/multiple-features-notation.png)

## Cost Function for Linear Regression with multiple features**
![Cost Function](../../images/cost-function-multiple-features.png)

## Vectorization

The w and x are represented as vectors ( stored as numpy arrays in code ), which makes calculations easier and also faster.

![Vectorization](../../images/vectorization.png)

>[NumPy and Vectorization](../../labs/Course%201/Week%202/C1_W2_Lab01_Python_Numpy_Vectorization_Soln.ipynb)

## Gradient Descent for Multiple Linear Regression

![Gradient Descent for Multiple Linear Regression](../../images/gradient-descent-for-multiple-linear-regression.png)

>[!NOTE]
Normal Equation is an alternative method for finding w and b ( only for linear regression ).  
This other method does not need an iterator like gradient descent algorithm. Some disadvantages of the normal equation method are; first unlike gradient descent, this is not generalized to other learning algorithms. The normal equation method is also quite slow if the number of features is large. Almost no machine learning practitioners should implement the normal equation method themselves but if you're using a mature machine learning library and call linear regression, there is a chance that on the backend, it'll be using this to solve for w and b. 

>[Implementing Gradient Descent In Code](../../labs/Course%201/Week%202/C1_W2_Lab02_Multiple_Variable_Soln.ipynb)

## Feature Scaling

Feature Scaling is a technique that enables gradient descent to run much faster. 

For Ex) While predicing the price of a house using two features x1 the size of the house and x2 the number of bedrooms. Let's say that x1 typically ranges
from 300 to 2000 square feet. And x2 in the data set
ranges from 0 to 5 bedrooms. So for this example, x1 takes on
a relatively large range of values and x2 takes on a relatively
small range of values. 

We notice that when a possible range of values of a feature is large, like the size and square feet which goes all the way up to 2000, It's more likely that a good model will learn to choose a relatively small parameter value, like 0.1.   
Likewise, when the possible values of the feature are small, like the number of bedrooms, then a reasonable value for its parameters will be
relatively large like 50. 

>[!IMPORTANT]
**When the range of values of a feature is large, its respective parameter is observed to be small and vice versa.**

And this is because a very small change to w1 can have a very large impact on the estimated price and that's a very large impact on the cost J. Because w1 tends to be multiplied by a very large number, the size and square feet. In contrast, it takes a much larger change in w2 in order to change the predictions much. And thus small changes to w2, don't change the cost function nearly as much. 

![Feature Scaling Introduction](../../images/feature-scaling-introduction.png)

This is what might end up happening if we were to run gradient descent, in thus training data as it is. **Because the contours are so tall and skinny gradient descent may end up bouncing back and forth for a long time before it can finally
find its way to the global minimum.**

**In situations like this, a useful thing to do is to scale the features. This means performing some transformation of your training data so that x1 say might now range from 0 to 1 and x2 might also range from 0 to 1. The key point is that the scale of x1 and x2 are both now in comparable ranges of values to each other. And if you run gradient descent on this rescaled transformed data, then the contours will look more like this more like circles and less tall and skinny. And gradient descent can find a much more direct and faster path to the global minimum.**

### Ways to implement feature scaling

1. **Divide by Highest Value of the feature, so the upper bound is always 1**  
Ex) If x1 ranges from 3-2000, divide by 2,000, the maximum of the range. 
Now x1 will range from 0.15 up to 1. Similarly, since x2
ranges from 0-5, dividing by 5, x2 will now range from 0-1.

2. **Mean Normalization**  
Replace every element x1 with: **(x1-mean) / (upperbound-lowerbound)**  
The ranges will always be from -1 to 1 now

For Ex) If 300<=x1<=2000, and the average is 600, after mean normalization, -0.18<=x1<=0.82

3. Z-score Normalization 

To implement z-score normalization, first we need to calculate standard deviation ( denoted by sigma )

Replace every element x1 with: **(x1-mean) / standard deviation**

As a rule of thumb, when performing feature scaling, you might want to
aim for getting the features to range from around -1 to +1 for each feature x. 
But these values, negative one and plus one can be a little bit loose. If the features range from negative three to plus three or negative 0.3 to plus 0.3, all of these are completely acceptable.