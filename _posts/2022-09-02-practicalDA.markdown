---
layout: post
author: "Adam Breitholtz, Fredrik Johansson"
title: "Practicality of generalization guarantees for unsupervised domain adaptation with neural networks"
date:   2022-09-02 09:00:00 +0100
venue: UAI 2022
image: assets/posts/boundimg.png
paper: https://openreview.net/forum?id=vUuHPRrWs2
categories: blog
abstract: >-
  Understanding generalization is crucial to confidently engineer and deploy machine learning models, especially when deployment implies a shift in the data domain. For such domain adaptation problems, we seek generalization bounds which are tractably computable and tight. If these desiderata can be reached, the bounds can serve as guarantees for adequate performance in deployment. However, in applications where deep neural networks are the models of choice, deriving results which fulfill these remains an unresolved challenge; most existing bounds are either vacuous or has non-estimable terms, even in favorable conditions. In this work, we evaluate existing bounds from the literature with potential to satisfy our desiderata on domain adaptation image classification tasks, where deep neural networks are preferred. We find that all bounds are vacuous and that sample generalization terms account for much of the observed looseness, especially when these terms interact with measures of domain shift. To overcome this and arrive at the tightest possible results, we combine each bound with recent data-dependent PAC-Bayes analysis, greatly improving the guarantees. We find that, when domain overlap can be assumed, a simple importance weighting extension of previous work provides the tightest estimable bound. Finally, we study which terms dominate the bounds and identify possible directions for further improvement.
---

## A survey of the field of unsupervised domain adaptation bounds show us that only a few of them are actually computable

![Policy evaluation with prototypes](/assets/posts/cbope.png){:class="post-general-image"}

The increasing amount of available data on medical interventions and reported outcomes creates opportunities to search for new clinical policies. As an example, researchers have employed reinforcement learning algorithms to learn new strategies for the management of sepsis [1]. However, for such a policy to be used in practice, it is of utmost importance that its performance, or value, can be reliably estimated. Ideally, the estimated value of this target policy should be higher than the value of the—often unknown—behavior policy followed by clinicians in the observed data.

While the value of the behavior policy can be easily estimated by averaging outcomes in the observed data, the value of the target policy is fundamentally unknown. Off-policy evaluation (OPE) refers to the problem of estimating the target policy value using data collected under the behavior policy. A standard method for OPE is importance sampling (IS), where each observed outcome is weighted by the probability ratio of taking the actions preceding that outcome under the target policy and the behavior policy, respectively. When the behavior policy is unknown, it must be estimated from data before the IS average can be computed.

Even though importance sampling is a popular method for OPE, it suffers from high variance when there are significant differences between target and behavior policies. By inspecting the IS weights, it is possible to collect individual samples for which the policies differ, but this approach does not describe patterns in differences between polices. To address this problem, we suggest estimating the unknown behavior policy using prototype learning [2], which gives us a set of interpretable prototype cases from the observed data. The prototypes are selected by the learning algorithm, and for a specific input, e.g., a patient, the model estimates the behavior policy by comparing the input to the prototypes in a learned representation. The idea is reminiscent of how physicians use their experience from previous patients when treating new ones.

We use the learned prototypes as a diagnostic tool for OPE. By inspecting the behavior and target policies for each of the prototypes, we obtain a condensed overview of differences between the policies. A domain expert can reason about the validity of the target policy and assess whether the data supports evaluating it using importance sampling. Additionally, we use the prototypes to divide estimated policy values into prototype-based components, allowing us to describe situations when it may be beneficial to follow the target policy instead of the behavior policy, and vice versa.

If you are interested, you are welcome to read our UAI 2022 paper [3], where we elaborate on the prototype idea and demonstrate it using a real-world example of sepsis management.

* [1] David A. McAllester. A PAC-Bayesian Tutorial with A Dropout Bound. arXiv e-prints, 1307:
arXiv:1307.2118, July 2013
* [2] Adam Breitholtz and Fredrik Johansson. Practicality of generalization guarantees for unsupervised
domain adaptation with neural networks. In submission, 2022.
