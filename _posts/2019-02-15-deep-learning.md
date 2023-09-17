---
layout: post
title: deep learning
categories: Others
description: 搭建个人博客
keywords: github pages, github, personal blog
---
Today's content is about the neural network architecture

Initialization is extremely important: determines how statistics of outputs behave; determins how well gradients flow in the beginning of training; limit use of full capacity of the model if done improperly.

deeper networks are more sensitive to initialization. wtih a deeper netowrk, standard deviations of the activation output reduces significantly.

Key takeaway: initilization matters the activation statistics, and therefore gradient statistics; if gradients are small, no learning will occur and no improvement is possible. 

Normalization can improve gradient flow and learning. Normalization method iccludes: substract mean, divide by standard deviation. 
 PCA method. 

Optimizer--
impactful issues: 

1. Noisy gradient estimates--batches, the gradient that we obtained has high variance
2. Saddle points  we need to check the second derivatives
3. III-conditioned loss surface

   
update vilocity
$v_i=\beta v_{i-1}+ \frac{\partial L}{\partial w_{i-1}}$


$w_i=w_{i-1}-\alpha v_{i}$

Steepest direction- use Hassian Matrix

Problem: network can learn to rely strong on a few features that work really well.
solve: flip the coin to determine whether to keep that node or not. i.e., whether to mask that node out for each iteration.

Observe the change of loss function: 1) after adding regularization, the loss function should increase
2) tiny loss change -> too small of a learning rate, loss turn to NaNs -> too high of a learning rate.

