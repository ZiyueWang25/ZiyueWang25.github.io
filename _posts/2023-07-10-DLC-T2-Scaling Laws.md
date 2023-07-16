---
layout: post
title: Replicating Scaling Laws by using MNIST data
date: 2023-07-10
description: I tried to replicating scaling laws result by using MNIST data. Here is what I learnt.
tags: ML
categories: AI
giscus_comments: true

---

I started following [Deep Learning Curriculum](https://github.com/jacobhilton/deep_learning_curriculum/tree/master) written by [Jacob Hilton](https://www.jacobh.co.uk/) and here is what I learnt from the exercise in [Topic 2 - Scaling Laws](https://github.com/jacobhilton/deep_learning_curriculum/blob/master/2-Scaling-Laws.md). My solution is written in Colab [T2-ScalingLaws-solution.ipynb](https://colab.research.google.com/drive/1xTpfj6xADQYdUudnZE9AWMUzyr8DBoU6?usp=sharing)

It took me around 15 hours to finish the exercise. Throughout the process I learnt:
1. How to vary the CNN width and training data to follow scaling laws experimentation set up.
2. How to use Pytorch lighting learning rate finder to adjust the learning rate based on model size.
	1. use `callbacks.LearningRateFinder` from pytorch lighting and do some experimentation to find the proper minimum and maximum learning rate to search from. Plot the learning rate to make sure the result looks right. ![](https://i.ibb.co/BBN4gyc/lr-plot.png)
3. How the compute-efficient model size varies with compute.
	1. To approximate the relationship between compute and loss, we can use [Cubic Root Function](https://www.cuemath.com/calculus/cube-root-function/). We need to train more episodes to enable an accurate approximation. 

![](https://i.ibb.co/41vg6jL/download-2.png)

![](https://i.ibb.co/zNDhTpD/download.png)
![](https://i.ibb.co/dgSp0MN/download-1.png)