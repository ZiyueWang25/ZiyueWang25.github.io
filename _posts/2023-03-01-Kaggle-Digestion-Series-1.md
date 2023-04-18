---
layout: post
title: KDS - Google Universal Image Embedding
date: 2023-03-01
description:
tags: Kaggle
categories: AI

---
- Competition End time: 2022-10-17
- Submission Format: notebook <= 9h

# Key Features
1. No training data provided. 
2. Ensemble cannot easily work. [thread](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/340546#1876558])

# [Evaluation](https://www.kaggle.com/competitions/google-universal-image-embedding/overview/evaluation)
mean Precision @ 5 metric + a small modification to avoid penalizing queries with fewer than 5 expected index images.

$mP@5 = \frac{1}{Q} \sum_{q=1}^Q \frac{1}{\min(n_q, 5)} \sum_{j=1}^{\min(n_q, 5)} rel_q(j)$

- embedding dimension should be <= 64
- compatible with TensorFlow 2.6.4 or Pytorch 1.11.0

The host will use k-NN (k=5) to lookup for each test sample, using the Euclidean distance between test and index embeddings.

# [Data](https://www.kaggle.com/competitions/google-universal-image-embedding/data)
**No training data provided.**
Here is the distribution of test data.
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F3258%2Fa02c90ad69a049b11a39bd38abcde2cb%2Fdomains.png?generation=1657141626387503&alt=media)
1. External data thread: https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/337384

# Great Notebooks
1. [CLIP-TF-Train-Example](https://www.kaggle.com/code/motono0223/guie-clip-tensorflow-train-example)
	1. CLIP + Arcface + TPU training.
2. [GCVIT](https://www.kaggle.com/code/awsaf49/gcvit-global-context-vision-transformer)
	1. Global Context Vision Transformer
3. [Understand Comp Domain and ImageNet 21k Labels](https://www.kaggle.com/code/evilpsycho42/understand-comp-domain-and-imagenet-21k-labels)
	1. Understanding comp domain and labels

# Solutions

1. [1st place solution](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/359316)
	1. Using [pre-trained weights](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/340043) w/o training or fine-tuning first.
	2. CLIP [Github](https://github.com/mlfoundations/open_clip)
	3. [ArcFace](https://arxiv.org/abs/1801.07698) 
	4. Add datasets to training list **iteratively** to save time and maintain good performance
	5. unfreeze the backbone after linear head is well trained, so we don't need to worry about the random linear head would affect the backbone weights
		1. use 10 times lower initial learning rate.
		2. Easy to get overfit and linear projection weights jumped sharply.
		3. So freeze linear head to train and add dropout to fully connection layer.
	6. Clever ensemble to overcome different F(C, X) issues
		1. resolution 224 + resolution 280
	7. LAION-5B CLIP Model [blog](https://laion.ai/blog/large-openclip/)
2. [2nd place solution](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/359525)
	1. dynamic margin
	2. stratified learning rate when training non-backbone part.
3. [4th place solution](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/359487)
4. [5th place solution](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/359161)
5. The rest [thread](https://www.kaggle.com/competitions/google-universal-image-embedding/discussion/359948)
