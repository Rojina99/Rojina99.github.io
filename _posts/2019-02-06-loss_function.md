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
