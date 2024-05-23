# Chapter 5: Bayesian Networks and Data

In the [previous chapter](../chapter-4-knowledge-modeling-and-probabilistic-reasoning.md), we described the application of Bayesian networks for evidential reasoning. All available knowledge was manually encoded in the Bayesian network in that example. In this chapter, we additionally use data for defining Bayesian networks. This provides the basis for the following chapters, which will present applications that utilize machine-learning for generating Bayesian networks entirely from data.

For machine learning with BayesiaLab, concepts derived from information theory, such as entropy and mutual information, are particularly important and should be understood by the researcher. However, these measures are not nearly as familiar to most scientists as common statistical measures, e.g., covariance and correlation.

### Example: House Prices in Ames, Iowa&#x20;

We present a straightforward research task to introduce these presumably unfamiliar information-theoretic concepts. The objective is to establish the predictive importance of a range of variables concerning a target variable. The domain of this example is residential real estate, and we wish to examine the relationships between home characteristics and sales prices. In this context, it is natural to ask questions related to variable importance, such as, which is the most important predictive variable pertaining to home value? By attempting to answer this question, we can explain what entropy and mutual information mean in practice and how BayesiaLab computes these measures. In this process, we also demonstrate a number of BayesiaLab’s data-handling functions.

The dataset for this chapter’s exercise describes the sale of individual residential properties in Ames, Iowa, from 2006 to 2010. It contains a total of 2,930 observations and a large number of explanatory variables (23 nominal, 23 ordinal, 14 discrete, and 20 continuous). This dataset was first used by De Cock (2011) as an educational tool for statistics students. The objective of their study was the same as ours, i.e., modeling sale prices as a function of the property attributes.

To make this dataset more convenient for demonstration purposes, we reduced the total number of variables to 49. This pre-selection was fairly straightforward as numerous variables essentially do not apply to homes in Ames, e.g., variables relating to pool quality and pool size (there are practically no pools) or roof material (it is the same for virtually all homes).

### The Workflow in Detail&#x20;

{% content-ref url="data-import-and-discretization.md" %}
[data-import-and-discretization.md](data-import-and-discretization.md)
{% endcontent-ref %}

{% content-ref url="node-names-long-names-and-node-comments.md" %}
[node-names-long-names-and-node-comments.md](node-names-long-names-and-node-comments.md)
{% endcontent-ref %}

{% content-ref url="uncertainty-entropy-and-mutual-information.md" %}
[uncertainty-entropy-and-mutual-information.md](uncertainty-entropy-and-mutual-information.md)
{% endcontent-ref %}

{% content-ref url="parameter-estimation.md" %}
[parameter-estimation.md](parameter-estimation.md)
{% endcontent-ref %}

{% content-ref url="naive-bayes-network.md" %}
[naive-bayes-network.md](naive-bayes-network.md)
{% endcontent-ref %}

### References

Dean De Cock. Ames, Iowa: Alternative to the Boston Housing Data as an End of Semester Regression Project. Journal of Statistical Education, 19(3), 2011.
