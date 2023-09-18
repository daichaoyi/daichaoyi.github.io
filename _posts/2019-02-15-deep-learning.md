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

Convolution Layers:
The problem of too many parameters: computation and memory inefficient
How to solve this problem? the input is only a small patch(segregate the picture into many small pathes.), it reduces to a smaller window K1*K2

<img width="1082" alt="Screen Shot 2023-09-17 at 5 30 35 PM" src="https://github.com/daichaoyi/daichaoyi.github.io/assets/50822172/c17b60f6-9a90-45c3-9817-eee7b10a9753">


The intuition of convolution: take the kernel and flip it or rotating it by 180 degrees, dot that kernel with all the different image patches or locations in the image. start from upper left, dot product between the nine values in the image and the kernel, also a bias term.
<img width="1007" alt="Screen Shot 2023-09-17 at 6 08 42 PM" src="https://github.com/daichaoyi/daichaoyi.github.io/assets/50822172/2ac6a1c1-85ff-45c1-8143-a434e1ae3b0c">

<img width="421" alt="Screen Shot 2023-09-17 at 8 05 32 PM" src="https://github.com/daichaoyi/daichaoyi.github.io/assets/50822172/31ef5ef9-7a2a-4200-8c33-7feff6dc1731">

the pixels on the margin of the picture will never be located in the center of the kernel, therefore, we should have paddings. The stride is unit that the kernel move. 

The purpose of pooling was to realize the Reduction of Dimensionality:
For example the max pooling take the maximum value from the kernel.


<img width="1104" alt="Screen Shot 2023-09-17 at 8 10 58 PM" src="https://github.com/daichaoyi/daichaoyi.github.io/assets/50822172/d4bf7332-91a5-424c-9f42-03f264fb5cce">






