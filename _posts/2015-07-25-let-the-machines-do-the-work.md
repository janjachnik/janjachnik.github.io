---
layout:     post
categories: vision machine learning
---

Yesterday I attended the [Institute of Mathematics and its Applications (IMA)](http://www.ima.org.uk/) summer lecture at the Royal Society. The talk, by Professor Terry Lyons, was asking what the Mathematics community has to offer as "a data tsunami sweeps our society". The talk reflected on something that is now starting to dominate the computer vision community; we need to let the machines do the work, and by that I mean machine learning.

> Even our most advanced mathematical models are not good enough to reliably represent highly complex systems.

Most problems we are trying to solve consist of transforming some input data **X** to some output **Y**. A simple physics example: **X** is the initial velocity of a projectile, **Y** is the distance the projectile will travel. A computer vision example: **X** is an image, **Y** tells us the likelihood it is an image of a cat.

The traditional model based approach to solving these problems is to use our knowledge of physics and the real world to write down a function **f** so that **Y = f(X)**. This approach can work incredibly well for relatively simply systems where the dynamics of the system are very well understood. For example, the [trajectory of a projectile](https://en.wikipedia.org/wiki/Trajectory_of_a_projectile). However, what is the function taking an image of a cat and returning the likelihood that there is a cat in the image? This is something that we can't write down with our current knowledge, so we turn to machine learning.

The machine learning approach is to use a large amount of data to _learn_ the function **f(X)**. The most basic example of this is [least squares fitting](http://mathworld.wolfram.com/LeastSquaresFitting.html). Back in college you may have tried to find the equation of a straight line that was the best fit to some data points - that is a basic form of machine learning. In computer vision we use machine learning to recognise pictures of cats by showing the machine lots of images of cats and lots of images which aren't of cats. The machine then learns the function **f** to decide if an image is a cat or not. 

So what does mathematics have to offer in this area? Machine learning techniques are already being used very effectively in computer vision and many other areas. However, we are also finding ways where they can easily be broken. I believe mathematicians can provide a rigorous analysis of how, when and why these techniques work and what their limitations are.
