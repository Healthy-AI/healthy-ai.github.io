---
layout: post
author:  "Hákon Valur Dansson, Lena Stempfle, Hildur Egilsdóttir, Alexander Schliep, Erik Portelius, Kaj Blennow, Henrik Zetterberg, Fredrik D Johansson"
title: "Predicting progression & cognitive decline in amyloid-positive patients with Alzheimer's disease"
date:   2021-03-15 09:00:00 +0100
venue: Alzheimer's Research & Therapy
image: assets/posts/mmse_change.png
paper: https://alzres.biomedcentral.com/articles/10.1186/s13195-021-00886-5
categories: blog
abstract: >-
  In Alzheimer’s disease, amyloid-β (Aβ) peptides aggregate in the brain forming CSF amyloid levels, which are a key pathological hallmark of the disease. However, CSF amyloid levels may also be present in cognitively unimpaired elderly individuals. Therefore, it is of great value to explain the variance in disease progression among patients with Aβ pathology. We studied the problem of predicting disease progression and cognitive decline of potential AD patients with established Aβ pathology using the Alzheimer’s Disease Neuroimaging Initiative (ADNI) database.
---

### Abstract

![Change in MMSE over time](/assets/posts/mmse_change.png){:class="post-general-image"}

In Alzheimer’s disease, amyloid-β (Aβ) peptides aggregate in the brain forming CSF amyloid levels, which are a key pathological hallmark of the disease. However, CSF amyloid levels may also be present in cognitively unimpaired elderly individuals. Therefore, it is of great value to explain the variance in disease progression among patients with Aβ pathology. We studied the problem of predicting disease progression and cognitive decline of potential AD patients with established Aβ pathology using the Alzheimer’s Disease Neuroimaging Initiative (ADNI) database.
A cohort of n=2293 participants, of whom n=749 were Aβ positive, was selected from the to study heterogeneity in disease progression for individuals with Aβ pathology. Aβ pathology status was determined based on the Aβ42/Aβ40 ratio. Due to the relatively low prevalence of Aβ pathology, models fit only to Aβ-positive subjects were compared to models fit to an extended cohort including subjects without established Aβ pathology, adjusting for covariate differences between the cohorts.

The best performing machine learning model achieved a performance of R2 = 0.388 predicting the change in MMSE scores two years after baseline using a linear regression model based on a cohort with weighted samples in the training cohort using all features at baseline. Similarly, a gradient boosting model with all subjects weighted equally predicted the change in diagnosis with high accuracy (F1 = 0.791) when using all features. For the most accurate predictions, our models combine variables measured at the baseline such as cognitive tests, CSF biomarkers, proteins and genetic markers. Among these, baseline cognitive tests scores were found to be the strongest predictors, accounting for most of the variance explained by all features, across models. Finally, we identified that even though the Aβ42/Aβ40 ratio is a good predictor for AD in the preclinical phase, the respective levels of Aβ are less useful in predicting progression among only Aβ-positive subjects. Baseline assessments of cognitive function accounts for the majority of variance explained in the prediction of two-year decline but is insufficient for achieving optimal results in longer-term predictions.
