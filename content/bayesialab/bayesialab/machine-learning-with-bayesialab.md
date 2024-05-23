# Machine Learning with BayesiaLab

* BayesiaLab features a comprehensive array of highly optimized algorithms to efficiently learn Bayesian networks from data (structure and parameters).&#x20;
* The optimization criteria in BayesiaLab’s learning algorithms are mostly based on information theory (e.g., the Minimum Description Length).&#x20;
* With that, no assumptions regarding the variable distributions are made. These algorithms can be used for all kinds and all sizes of problem domains, sometimes including thousands of variables with millions of potentially relevant relationships.

### Unsupervised Learning

* In statistics, “unsupervised learning” is typically understood to be a classification or clustering task. To make a clear distinction, we emphasize “structural” in “Unsupervised Structural Learning,” which covers a number of important algorithms in BayesiaLab.
* Unsupervised Structural Learning means that BayesiaLab can discover probabilistic relationships between many variables without having to specify input or output nodes. One might say that this is a quintessential form of knowledge discovery, as no assumptions are required to perform these algorithms on unknown datasets.

{% hint style="info" %}
See Also

* [Chapter 7: Unsupervised Learning](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-7-unsupervised-learning/)
* Webinar: Analyzing Capital Flows of Exchange-Traded Funds
{% endhint %}

### Supervised Learning

* Supervised Learning in BayesiaLab has the same objective as many traditional modeling methods, i.e., to develop a model for predicting a target variable.&#x20;
* Note that numerous statistical packages also offer “Bayesian Networks” as a predictive modeling technique. However, in most cases, these packages are restricted in their capabilities to one type of network, i.e., the Naive Bayes network.&#x20;
* BayesiaLab offers a much greater number of Supervised Learning algorithms to search for the Bayesian network that best predicts the target variable while also considering the complexity of the resulting network.&#x20;
* We should highlight the set of Markov Blanket algorithms for their speed, which is particularly helpful when dealing with many variables. In this context, the Markov Blanket algorithm can be an efficient variable selection algorithm.

{% hint style="info" %}
See Examples & Learn More

* Markov Blanket Learning Algorithms (9.0)
* Chapter 6: Supervised Learning
* Webinar: Diagnostic Decision Support
{% endhint %}

### Clustering

* Clustering in BayesiaLab covers both Data Clustering and Variable Clustering.
  * Data Clustering applies to creating a Latent Variable whose states represent groups of observations (records) that share some characteristics.&#x20;
  * Variable Clustering groups variables according to the strength of their relationships.&#x20;
* Multiple Clustering is one of the steps of BayesiaLab's Probabilistic Structural Equation Model (PSEM) workflow. It consists of iteratively using Data Clustering on subsets of data defined by Variable Clustering to create Latent Variables that represent the hidden causes that have been sensed by Manifest Variables. This can be considered as a kind of nonlinear, nonparametric, and nonorthogonal factor analysis.

{% hint style="info" %}
See Examples & Learn More

* Data Clustering (7.0)
* Variable Clustering (7.0)
* Multiple Clustering (9.0)&#x20;
* Chapter 8: Probabilistic Structural Equation Models Webinar: Factor Analysis Reinvented — Probabilistic Latent Factor Induction
{% endhint %}
