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

Before understanding the process of neural network optimization we have to understand loss function. Loss function also called cost function is simply a function representing difference between target (actual) output($$y$$) and predicted output($$y_{pred}$$). Neural network optimizers are usually focused on miniming this loss function. There are many loss function. Some of them will be discussed here.

1. Mean Squared Error:-
   It is function which calculates difference between targeted output and predicted output which is summed and the mean of the sum is taken. The function is represented as:
   
   $$ L = \frac{1}{n} \sum_{i=1}^{n}(y-y_{pred})^2 $$
   
   This function is mostly used for regression problems i.e. when the target output is continuous or numerical value prediction. For example:- bank transaction amount, number of sales each day.
   
   | Author |Ideal Book Price | Predicted Book Price| 
   |--------|-----------------|------------------|
   | Deepak | 100 | 95 |
   | Peter | 500 | 300 |
   | Rosel | 700 | 500 |
   
   
   Normalizing and embedding representaion of data results in
   
   | Author | Ideal Book Price | Predicted Book Price| 
   |--------|------------------|------------------|
   | 00 |0 | 0.13 |
   | 01 |0.667 | 0.33 |
   | 10 |1 | 0.63 |
   
   The normalization formula is represtented as:
   
   $$f(x) = \frac{(x−dL)(nH−nL)}{(dH−dL)} + nL$$
   
   Where, 
    x is value to be normalized,   
    dH and dL are high and low value of an attribute,          
    nH and nL are range of normalization i.e 0 to 1, -1 to 1, 100 to 100, ...
   
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
    
    $$ CE = -\sum_{i}^{n}y_{i} log (^y_{i}) $$
    
    $$ L=−1nn∑i=1[y(i)log(^y(i))+(1−y(i))log(1−^y(i))] $$
    
    
    
 
