---
layout: post
title: Replicating Diffusion Models on MNIST
date: 2023-06-11
description: I tried to replicating diffusion model (DDPM & DDIM) by following DeepLearningAI course and trained it on MNIST.
tags: Project
categories: AI
giscus_comments: true
---

My solution is written in colab [DiffusionModel-DeepLearningAI-Pytorch.ipynb](https://colab.research.google.com/drive/1LcxLcVfxeFQWlEEWVTBx_LfNMaY3CoNg?usp=sharing)

It took me around 8 hours to implement it and 2 hours are spent on gathering the proper data. Throughout the process I learnt:

1. The details of DDPM and DDIM algorithm and how diffusion model works
2. Manipulating image data for diffusion modeling and demonstration purpose
3. classifier-free guided diffusion to let the model generate, `even` or `divisible by 3` digits.
