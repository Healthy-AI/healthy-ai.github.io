---
layout: post
author:  "Adam Breitholtz, Fredrik Johansson"
title: "Practicality of generalization guarantees for unsupervised domain adaptation with neural networks"
date:   2022-09-02 13:00:00 +0100
venue: In submission
image: assets/posts/cbope.png
paper: https://openreview.net/forum?id=vUuHPRrWs2
categories: blog
abstract: >-
Understanding generalization is crucial to confidently engineer and deploy machine learning models, especially when deployment implies a shift in the data domain. For such domain adaptation problems, we seek generalization bounds which are tractably computable and tight. If these desiderata can be reached, the bounds can serve as guarantees for adequate performance in deployment. However, in applications where deep neural networks are the models of choice, deriving results which fulfill these remains an unresolved challenge; most existing bounds are either vacuous or has non-estimable terms, even in favorable conditions. In this work, we evaluate existing bounds from the literature with potential to satisfy our desiderata on domain adaptation image classification tasks, where deep neural networks are preferred. We find that all bounds are vacuous and that sample generalization terms account for much of the observed looseness, especially when these terms interact with measures of domain shift. To overcome this and arrive at the tightest possible results, we combine each bound with recent data-dependent PAC-Bayes analysis, greatly improving the guarantees. We find that, when domain overlap can be assumed, a simple importance weighting extension of previous work provides the tightest estimable bound. Finally, we study which terms dominate the bounds and identify possible directions for further improvement.
---

## A survey of the field of unsupervised domain adaptation bounds show us that only a few of them are actually computable

![Minimum bound values achieved](/assets/posts/cbope.png){:class="post-general-image"}

In sensitive applications such as healthcare we are generally concerned with not only the performance of our models on training data; but also when we apply them to unseen data which might come from a different distribution. In these situations we generally do not have access to labeled data which puts us in the unsupervised domain adaptation setting. Generalization bounds in this setting are generally used for model selection or as inspiration for new algorithms. However, if we are interested in performance guarantees on out-of-distribution samples the literature is more sparse. We set out to remedy this by investigating if there are bounds which can satisfy two specific desiderata: computability, tractability and estimability.

We survey the field of domain adaptation generalization bounds and find that most of the existing literature cannot satisfy these desiderata even under the strong assumptions of covariate shift and overlapping support. We identify bounds based on the PAC-Bayes framework as the most promising for achieving computable bounds. We compute and compare two bounds from the literature with two extension of previous work by McAllester [1] with importance weighting and MMD.
If you are interested you are welcome to read more about this in our paper [2]. In it we compute several domain adaptation bounds based on the PAC-Bayes framework and investigate their tightness for different image classification tasks.

* [1] David A. McAllester. A PAC-Bayesian Tutorial with A Dropout Bound. arXiv e-prints, 1307:
arXiv:1307.2118, July 2013
* [2] Adam Breitholtz and Fredrik Johansson. Practicality of generalization guarantees for unsupervised
domain adaptation with neural networks. In submission, 2022.
