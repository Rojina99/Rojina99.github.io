---
title: "Loss Function"
date: 2019-02-06
tags: [machine learning, data science, neural network, loss function, cost function]
header:
  image: "/images/introduction/intro.jpg"
excerpt: "Machine Learning, Data Science"
mathjax: "true"
gallery:
   - image_path: /images/parameters/gd.png
     alt: "gradient descent"
     url: /images/parameters/gd.png
     title: "Figure 1"
   - image_path: /images/parameters/lr_gd.png
     alt: "gradient descent for lower learning rate and higher learning rate"
     url: /images/parameters/lr_gd.png
     title: "Figure 2"
---

Before understanding the process of neural network optimization we have to understand loss function. Loss function also called cost function is simply a function representing difference between target or actual output($$y$$) and predicted output($$y_{pred}$$). Neural network optimizers are usually focused on miniming this loss function. There are many loss function. Some of them will be discussed here.

1. Mean Squared Error:-
   It is function which calculates difference between targeted output and predicted output which is summed and the mean of the sum is taken. The function is represented as:
   
   $$ L = \frac{1}{n} \sum_{i=1}^{n}(y-y_{pred})^2 $$
   
   This function is mostly used for regression problems i.e. when the target output is continuous or for numerical value prediction. For example:- bank transaction amount, number of sales each day.
   
   Let's, look at a table having continuous result: 
   
   | Author |Ideal Book Price | Predicted Book Price| 
   |--------|-----------------|------------------|
   | Deepak | 100 | 95 |
   | Peter | 500 | 300 |
   | Rosel | 700 | 500 |
   
   
   Normalizing and embedding representaion of above data results follwing table:
   
   | Author | Ideal Book Price | Predicted Book Price| 
   |--------|------------------|------------------|
   | 00 |0 | 0.13 |
   | 01 |0.667 | 0.33 |
   | 10 |1 | 0.63 |
   
   The normalization formula is represtented as:
   
   $$f(x) = \frac{(x−dL)(nH−nL)}{(dH−dL)} + nL$$
   
   Where, 
    > x is value to be normalized,   
    > dH and dL are high and low value of an attribute,          
    > nH and nL are range of normalization i.e 0 to 1, -1 to 1, 100 to 100, ...
   
   And denormalization formula to get original value is given by formula:
   
   $$f(x) = \frac{(dL−dH)x−(nH·dL)+dH·nL}{(nL−nH)}$$
   
   Then the MSE error is calculated as:
   
   $$ L = \frac{1}{3}[(0-0.13)^2 + (0.667-0.33)^2 + (1-0.63)^2] $$
   $$ L = 0.0891 $$
   
   The error value is improved i.e. becomes less after several optimization epoch and iterations. 
   
 2. L1 loss:-
    It is also called least absolute error or least absolute deviation. It is calculated by taking sum of absolute differences between targeted output($$ y $$) and predicted output($$ y_{pred} $$). The formula is represented as:
    
    $$ L = \sum_{i=1}^{n}|y-y_{pred}|^2 $$
    
    It is used in regression problem and the activation function for final layer would be linear.
    
 3. L2 loss :-
    It is also called least squared error. It is the sum of squares of targeted output ($$ y $$) and predicted output ($$ y_{pred} $$) as represented by given formula:
    
    $$ L = \sum_{i=1}^{n}(y-y_{pred})^2  $$
    
    Similarly, it is used in regression problem and uses linear activation function in final layer. But it is usually preferred over L1 error because it estimates mean whereas L1 estimates median value. But, we know that mean is extremely affected by presence of outliers. So, in presence of outliers L1 is preffered over L2 error function.
    
 4. Cross Entropy Loss:
    This loss is also called log loss. It is represented by formula:
    
    $$ CE = -\sum_{i}^{n}y_{i} log (\hat{y}_{i}) $$
    
    In case of binary classification i.e. n=2.
    
    $$ CE = -(y_{i}log(\hat{y}_{i}) + (1-y_{i})log(1-\hat{y}_{i})) $$
    
    When, y_{i}(Actual Output) is 1 second half of function is zero and when y{i} is 0 first half is zero. It thus calculates multiplication of log of predicted probability with actual class. The predicted probalitity is ranged from 0 to 1. If the difference between actual value and predicted value is small the cross entropy loss will be small else the loss will increase logarithimically. Binary classification problen has output in the formsat of true or false, 0 or 1. So, sigmoid activation function is implemented at final layer.
    
   First formula can be implemented for multi class classification problem with softmax as classifier in final layer.
   In this kind of problem actual output will be in the format [0 0 1 0 0] and predicted outcome will be like [0.10 0.11 0.4 0.11 0.28]. Here, the sum of predicted output classes is 1. 
   
   **Note:** *Since, log of 0 is undefined. So, to avoid this scenario a small value like 1e-13 is added to value inside  log function.*
   
These are some of the popular loss functions. We will discuss backpropagation algorithm in next post.
