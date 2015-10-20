---
layout: post
title:  "Machine Learning"
date:   2015-10-20 19:24:11
categories: machine-learning self-study
---

# Machine Learning


## Introduction 

## Supervised vs Unsupervised Learning

## Linear regression using one variable
Linear regression is a supervised learning problem wherein we take a training dataset and create a continous model out of it to predict future values
Linear regression using one variables tried to predict one value (called dependent variable) using another ( called independent variable)

### Hypothesis function
A hypothesis function is a model which tries to predict the dependent variable given any independent variable
For one vraibel this is represented as 

````
h(x) = p1 + p2*x 
````

### Cost Function

Cost function is a function to tell the validity of a given hypothesis and is typically given as the mean squared difference between values obtained from hypothesis function and actual data in training dataset. Higher the cost of a hypothesis , lesser is its accuracy. A hypothesis with 0 cost means its fits each one fo the data points perfectly.

````
J(h(x)) = 1/2m * sum( (h(x) - y)^2)
````

which can be simplified as 

````
J(p1,p2) = 1/2m * sum( (p1 + p2*x -y) ^2)
````

where

- p1 = parameter 1 of hypothesis
- p2 = parameter 2 of hypothesis
- m = length of training set data
- x = element of x vector ( independnet variable)
- y - element of y vectory (dependenct variable)  


Note that Cost function is a function of p1 and p2 only as x and y are given values   


### Gradient descent

Now that we have a hypthesis and a cost function to calculate its accuracy, we should be able to come up with a way to get good values for p1 and p2 so that we have a hypothesis with least cost. This is done by gradient descent

Gradient descent is done by plotting a 3D plot of p1, p2 and its cost for entire dataset. The most appropriate hypothesis can be retrieved by taking the "pit" of this plot. Given any point on this point, we can acertain which direction to move to the pit of the plot by noting its derivative which is tangent of line to that point. We do this till we get a point with tangent = 0 which means it is the pit of the plot. 

In general , gradient descent can be defined as 
````
repeat until convergence {
	p1 = p1 - l * d/dp1 (J(p1,p2))
	p2 = p1 - l * d/dp2 (J(p1,p2)) 
}
where l is the learning rate (also called alpha)
````

Specifically for Linear regression for one variable , this can be written as 

````
repeat until convergence {
	p1 = p1 - l * d/dp1 (1/2m * sum( (p1 + p2*x -y) ^2))
	p2 = p2 - l * d/dp2 (1/2m * sum( (p1 + p2*x -y)^2 ) 
}
````

which can be shortened to 

````
repeat until convergence {
	p1 = p1 - (l/m) *  sum( (p1  -y) ) 
   p2 = p2 - (l/m) *  sum( (p2*x -y))
}

````




 







