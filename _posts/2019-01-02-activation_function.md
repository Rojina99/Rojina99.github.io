---
title: "Activation Function"
date: 2018-12-24
tags: [machine learning, data science, neural network, activation function]
header:
  image: "/images/introduction/intro.jpg"
excerpt: "Machine Learning, Data Science"
mathjax: "true"
gallery:
   - image_path: /images/ann/ann_math.jpg
     alt: "activation ann"
     url: /images/ann/ann_math.jpg
     title: "Figure 1"
---

The function applied at neurons of a neural network to get output for provided input values is Activation Function. We can see the function in given figure:

{% include gallery %}

Here we can see the summation of outputs of network is passed through activation function. So, the output of the network y looks like:

$$y = A(x1*w1+ x2*w2+ ....xn*wn + b)$$

So, why do we need activation function then ?

The activation fucntion is introduced in the network due to following reasons:

1. To introduce non-linearitites in the neural network. If we pass layers of neural network through linear functions only then the output provided will also be linear output.
   It might be able to learn some simple data but will not be able to comprise the complexities of many machine learning datas which have many features as input.
   It might also not generate the weight values required for generalized dataset.
2. It simply determines whether the neuron most be activated or not. It acts as threshold to the neuron. It is used to predict the information on the basis of relevance of provided input. Let us, take example of sigmoid activation function in which is represnted by formula:
   $$f(x) = 1/(1 + e^-x)$$
   Here, the value of function ranges from 0 to 1 when e^x is 0 or infinity respectively.
   Thus, neurons are activated when the value of activation function is greater than zero and is not when the value approaches zero. Thus the function acts as threshold. 
3. It limits the value to be learned in required range. Otherwise output of neural network might range from -inf to inf. Thus, producing no relevant results.

There are many variations of activation fucntion. But, three of them are used extensively. They are:

1. Sigmoid Activation function:

  <img src="{{ site.url }}{{ site.baseurl }}/images/actv/sigmoid.jpg" alt="Sigmoid activation function">
  <img src="{{ site.url }}{{ site.baseurl }}/images/actv/tanh.png" alt="Tanh activation function">
  <img src="{{ site.url }}{{ site.baseurl }}/images/actv/relu.jpg" alt="Relu activation function">
