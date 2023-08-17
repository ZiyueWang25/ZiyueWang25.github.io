---
layout: post
title: Replicating Decoder-only Transformer by using William Shakespeare Corpus
date: 2023-06-19
description: I tried to replicating the Decoder-only transformer by following "Attention is all you need" paper and trained it on William Shakespeare's work.
tags: ML
categories: AI
giscus_comments: true

---

I started following [Deep Learning Curriculum](https://github.com/jacobhilton/deep_learning_curriculum/tree/master) written by [Jacob Hilton](https://www.jacobh.co.uk/) and here is what I learnt from the exercise in [Topic 1 - Transformer](https://github.com/jacobhilton/deep_learning_curriculum/blob/master/1-Transformers.md). **My solution is written in Colab [T1-Transformers-solution.ipynb](https://colab.research.google.com/drive/18oP7mmz6sgC3pUembsOLdS6jSwlVbmIv?usp=sharing)**

It took me around 20 hours to finish the exercise and it totally worth it. Throughout the process I learnt:
1. How to implement the transformer model end-to-end.
2. How to gather and clean the data for transformer model
3. How to implement positional embedding, Attention, FNN, Residual Connection and put all of them together into transformer model.
4. Switching between `LayerNorm(x + SubLayer(x))` and `x + SubLayer(LayerNorm(x)` doesn't affect model performance.
5. How to program in Pytorch more fluently and gathered a bunch of utility function for later usage.
6. How to debug the model by using gradient flow and `torchviz.make_dot` to check model structure clearly.
