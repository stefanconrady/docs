# 🇫🇷 BayesiaLab Independence of Causal Influence Models

Presented at the [9th Annual BayesiaLab Conference](./) on October 15, 2021.

### Abstract <a href="#h2_148496644" id="h2_148496644"></a>

One of the most challenging tasks when building Bayesian networks with a group of subject matter experts is the parametrization of the model, i.e., the quantification of the probabilistic relationships. Indeed, with the default tabular representation of Conditional Probability Distributions (CPDs), the number of probabilities to be elicited grows exponentially with respect to the number of parent nodes.

As a result, there is not only a problem regarding the time it takes to fill in these large Conditional Probability Tables (CPTs) but also a problem of consistency between the elicited probabilities.

Even though formulas offer an effective way to fill CPTs, it is not really possible to use them "live" in a brainstorming session because they can seem quite complex and abstract to experts. An elegant alternative approach is determining whether the model requires considering all interactions between the parent nodes. If not, we can "divorce" the parent nodes and effectively represent their Independent Causal Influence (ICI) on the child node.

BayesiaLab 10 includes a new tool for automatically generating different types of ICI models. Experts can choose the Combination Function (Or, And, Max, Min, Sum, Vote, Average) and then elicit Local Causal Effects using simple counterfactual questions.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/2021-Conference/Lionel-Jouffe/ICI\_1280x657.png)\


ICI models are not only useful for modeling expert knowledge but can also be useful in the context of [Supervised Learning](https://bayesia.clickhelp.co/articles/bayesialab/learning-supervised-learning). The model described above is indeed a Bayesian Regression Model. When data is available, [Bayesian Parameter Updating](https://bayesia.clickhelp.co/articles/bayesialab/inference-parameter-updating) can be utilized to automatically estimate the Local Effects.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1714865469/2021-10-15-Conference-Lionel-Jouffe_1_ihbhsh.mp4" %}

### About the Presenter

* Dr. Lionel Jouffe is co-founder and CEO of France-based Bayesia S.A.S. Lionel holds a Ph.D. in Computer Science from the University of Rennes and has worked in Artificial Intelligence since the early 1990s. While working as a Professor/Researcher at ESIEA, Lionel started exploring the potential of Bayesian networks.
* After co-founding Bayesia in 2001, he and his team have been working full-time on the development of BayesiaLab. Since then, BayesiaLab has emerged as the leading software package for knowledge discovery, data mining, and knowledge modeling using Bayesian networks. It enjoys broad acceptance in academic communities, business, and industry.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710353058/PhotoLionel_bnmsdw.webp" alt="" width="188"><figcaption><p>Dr. Lionel Jouffe</p></figcaption></figure>
