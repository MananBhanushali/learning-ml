# Cost Function

In order to implement linear regression ​the first key step is first to ​define something called a cost function. **​The cost function will tell us how well ​the model is doing so that ​we can try to get it to do better.**

![Squared Error Cost Function](../../images/linear-regression-squared-error-cost-fn.png)

**​J is the cost function that ​measures how big the squared errors are, ​so choosing w that minimizes these squared errors, ​makes them as small as possible, ​will give us a good model.** 

**​The goal of linear regression is to find ​the parameters w and ​b that results in ​the smallest possible value for the cost function J.**

​When we had only one parameter, w, ​the cost function had this parabolic curve. ​Now, in this housing price example ​that we have on this slide, ​we have two parameters, w and b. ​The plots becomes a little more complex. ​It turns out that the cost function ​also has a similar shape like a soup bowl, ​except in three dimensions instead of two.

![Cost Function Three Dimensions](../../images/cost-function-three-dimensions.png)
 
​Now, in order to look even more ​closely at specific points, **​there's another way of plotting ​the cost function J ​that would be useful for visualization, ​which is called a contour plot.** ​If you've ever seen a topographical map ​showing how high different mountains are, ​the contours in a topographical map are basically ​horizontal slices of the landscape of say, a mountain. ​It shows all the points, ​they're at the same height for different heights. 

![Cost Function Contour Plot](../../images/cost-function-contour-plot.png)

>[Cost Function Visualisation](../../labs/Course%201/Week%201/C1_W1_Lab04_Cost_function_Soln.ipynb)