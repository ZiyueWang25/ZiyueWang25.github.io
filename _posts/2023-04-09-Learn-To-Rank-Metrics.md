---
layout: post
title: Metrics in Learn-To-Rank (LTR) problems
date: 2023-04-09
description:
tags: Project
categories: AI
giscus_comments: true

---
Suppose we have `Q` queries, for each query `q`, it brings $$N_q$$ results and normally we care about the top `K` docs retrieved. 

All of the following metric is for 1 query, we need to average them to get an overall score for `Q` queries.
1. `Accuracy@K`: Whether top K results contain the relevant results.
	1. Formula: $$ A(K)=(\sum_{i=1}^K I(i)) > 0 $$. $$I(i)$$ is an indicator function suggesting whether the $$i_{th}$$ position is relevant or not.
2. `Precision@K`: How many relevant results among the top K.
	1. Formula: $$P(K) =\frac{1}{K}\sum_{i=1}^KI(i)$$.  
	2. Only for binary cases
3. `Recall@K`: How many relevant results among the top K compared with all relevant results.
	1. Formula: $$R(K) = \frac{1}{m}\sum_{i=1}^KI(i)$$. $$m$$ is the total number of relevant results overall.
	2. Only for binary cases
4. `AP@K` (Average Precision): the weighted mean of precision at each threshold; the weight is the increase in recall from the prior threshold.
	1. Formula: $$AP@K = \frac{1}{m}\sum_{k=1}^K P(k)I(k)$$
	2. A different way to represent $$AP@K$$: We can also use `Recall@K` here by using its delta format $$\Delta R(k) = R(k) - R(k-1)$$. It would be $$\frac{1}{m}$$ if a relevant result is at position $$k$$, otherwise it is 0. and it becomes $$AP@K = \sum_{k=1}^K P(k) * \Delta R(k)$$. In other words, it is the area under Precision-Recall curve.
	3. Only for binary cases
5. `RR` (Reciprocal Rank): reciprocal of the rank of the first relevant item in a ranked list.
	1. Formula: $$RR = \frac{1}{\text{rank of the first relevant item}}$$
	2. Only for binary cases.
6. `NDCG@K` (Normalized Discounted Cumulative Gain)
	1. `CG@K`: Sum of relevance of all results in a search result list $$CG@K = \sum_{k=1}^K rel(k)$$, $$rel(k)$$ is the relevance score of the result at $$k$$.
	2. `DCG@K`: Give earlier result higher weights: $$DCG@K = \sum_{k=1}^K\frac{2^{rel(k)} - 1}{ \log_2(k+1)}$$
	3. `NDCG@K`: normalize `DCG` by its perfect ranking result (a.k.an Ideal `DCG` (`IDCG`)) to reduce the effect that different search results can vary in length.
7.  Normalized Kendall tau distance at K:
	1. $$K_n@K(\tau_1, \tau_2) = \frac{K_d}{\frac{1}{2}n(n-1)} = \frac{2}{n(n-1)} \sum_{\{i,j\}\in \mathbb{K}, i < j} \bar K_{i,j}(\tau_1, \tau_2)$$. $$\mathbb{K}$$ is the set of unordered pairs of distinct elements among the top K in $$\tau_1$$ and $$\tau_2$$. $$\bar K_{i,j}(\tau_1, \tau_2) = 0$$ if $$i$$ and $$j$$ are in the same order in $$\tau_1$$ and $$\tau_2$$, otherwise 1. 
8.  Spearman Rho:
	1. Formula: $$\rho = \frac{cov(R(X), R(Y))}{\delta_{R(x)}\delta_{R(Y)}}$$


Reference:
1. https://en.wikipedia.org/wiki/Discounted_cumulative_gain
2. https://en.wikipedia.org/wiki/Kendall_tau_distance
3. https://towardsdatascience.com/normalized-discounted-cumulative-gain-37e6f75090e9