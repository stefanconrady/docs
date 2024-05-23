---
description: A Strategic Approach to Probabilistic Networks in Poultry and Stress
---

# 🇬🇧 Genes, Publicly Available Databases, and Bayesian Networks

Presented at the [9th Annual BayesiaLab Conference](./) on October 14, 2021.

### Abstract&#x20;

Exploring publicly available genetic data repositories, such as Gene Expression Omnibus or Array Express, represents a great possibility to collect data previously published and get a deeper insight into a particular field of genetics. In the field of poultry genetics, experimental designs evaluate only a relatively small number of birds per study, requiring the combination of multiple sources into one bigger dataset for further analysis, focusing on one variable of interest, such as stress. Bayesian networks are a useful tool to overcome this challenge, as they can deal with uncertainty and noise resulting from different experimental designs, discovering relationships that are not necessarily linear. Therefore, our goal was to identify genes associated with stress in chickens, invoking an approach to Bayesian networks that involved the identification of genes of interest, the reduction of the dimensionality, followed by the learning of the structure of the consensus Bayesian network. Initially, genes identified in a previously published study were extracted from two other datasets with a similar experimental design. Our dataset consisted of 50 chickens, 101 genes and their expression values, and the stress condition. As the number of genes was rather too large to apply Bayesian networks algorithms directly, a supervised Naïve Bayes algorithm was implemented. The top 10 genes that contributed the most to the stress condition were used to learn the structure of the Bayesian network by the software Banjo to search for the best consensus network. Our results showed that all genes, as well as the condition, were included in the overall structure of the consensus network, indicating that all were interconnected. Interestingly, WNT7A, the gene that contributed the most to the condition according to Naïve Bayes, was found in close association with it in the network. Additionally, HSPH1 also displayed a relationship with the condition. The discovery of these two genes could be further explored in future studies as genes related to stress resistance or stress resilience with the aim of improving the welfare of chickens bred under commercial environments.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1707771173/2021-10-14-Conference-Emiliano-Ariel-Videla-Rodriguez_xcb107.mp4" %}

### Presentation Materials

{% embed url="https://res.cloudinary.com/dvr3obmlj/image/upload/v1707771168/Emiliano-Rodriquez_hensqz.pdf" %}

### About the Presenter

Emiliano Ariel Videla Rodríguez\
School of Biology\
University of St Andrews\
St Andrews, Fife KY16 9TH\
United Kingdom

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1707771625/Emiliano-Ariel-Videla-Rodriguez_pjznzm.jpg" alt="" width="188"><figcaption><p>Emiliano Ariel Videla Rodríguez</p></figcaption></figure>
