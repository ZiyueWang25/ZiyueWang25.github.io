---
layout: post
title: RLHF from Shakespeare
date: 2023-08-16
description: I tried to finetune LLM with RLHF to generate positive tone message from Shakespeare Corpus. Here is what I learnt.
tags: ML
categories: AI
giscus_comments: true

---

I started following [Deep Learning Curriculum](https://github.com/jacobhilton/deep_learning_curriculum/tree/master)(DLC) written by [Jacob Hilton](https://www.jacobh.co.uk/) and here is what I experienced and learnt from the exercise in [Topic 7 - Alignment](https://github.com/jacobhilton/deep_learning_curriculum/blob/master/7-Alignment.md). **My solution is written in Github repository [RLHF-Shakespeare](https://github.com/ZiyueWang25/RLHF-Shakespeare)**

So the overall idea is to finetune Large Language Model (LLM) with Reinforcement Learning from Human Feedback (RLHF) to generate positive tone message from Shakespeare corpus. It takes the following 3 steps:
1. Pretrain a small GPT-2 structure model on William Shakespeare corpus
2. Train reward model with manually labeled positive and negative message
3. Use the reward model and RLHF method to finetune the pretrained model and get a model that can generate more positive tone Shakespeare-alike messages.

The complete evaluation and training result in shown in the repository. Please take a look if that interests you :) 

Here is what I didn't expected and learnt:
1. labeling message generating from pretraining model is hard: Let's be honest, the messages generated from the pretrained model is kinda like gibberish, even though they have  some sentence structure in it. This is mostly due to the fact that the pretrained model is small and the corpus is not big enough. I found the evaluation metric can start showing sign of overfitting soon (around epoch 6). The perplexity score in the end is still high (~20).  So in the end, I used an existing dataset, which contains some lines from the corpus directly, gathered from Conner Kissane.
2. RLHF is hard: there are several opponents: pretrained model, reward model and RL algorithm. Each part can has their limitation and potential bugs. So making it work from scratch is definitely a not easy problem. In the beginning, I am a bit frustrated to saw the finetuned model performs still similarly to the finetuned model but after investigating the reasons, I felt a bit relieved because it simply just hard to make it work in such a small scale...
3. Iteration is important: if the pretrained model is not good enough or the reward model is overfitted, then it is hard to make RLHF work. We'd better iteratively make the previous steps better instead of only focusing on the last step.

Hope you enjoy this blog post and feel free to reach out if you have any question or want to have more discussion!