# Minimum Description Length Score

### Definition

The **Minimum Description Length Score (MDL Score)** is derived from Information Theory and has been used extensively in the Artificial Intelligence community.

It consists of the sum of two components that estimate:

* the minimum number of bits required to represent a model, and
* the minimum number of bits required to represent the data given the model.

However, in the specific context of Bayesian networks, we need to explain the exact meaning and the notation of these two components:

* [Calculating Complexity: DL(B)](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/344/bayesialab/key-concepts/minimum-description-length-score/calculating-complexity-dl-b)[Calculating Fit: DL(D|B)](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/344/bayesialab/key-concepts/minimum-description-length-score/calculating-fit-dl-d-or-b)"the minimum number of bits required to represent a model" is denoted $$DL\left( {B} \right)$$  (="Description Length of the Bayesian network $$B$$") and refers to the structural complexity of the Bayesian network model $$B$$, which includes the network graph and all probability tables.
  * For brevity, we often use the shorthand "complexity" or "structure" to refer to $$DL\left( {B} \right)$$.
  * Small values of $$DL\left( {B} \right)$$ suggest a simple model structure, and large values a complex model.
  * The goal of this structural part is to apply Occam's Razor, or the law of parsimony, i.e., to choose the simplest hypothesis, all other things being equal.
* "the minimum number of bits required to represent the data given the model" is denoted $$DL\left( {D|B} \right)$$ (="Description Length of the data $$D$$ given the Bayesian network $$B$$") and refers to the likelihood of the data $$D$$ with respect to the Bayesia network model $$B$$.
  * The data likelihood is inversely proportional to the probability of the observed dataset, as inferred by the Bayesian network model.
  * Put simply,$$DL\left( {D|B} \right)$$ refers to the "fit" of the model to the data.
  * Small values of$$DL\left( {D|B} \right)$$ suggest a well-fitting model; large values, conversely, imply a poor fit.

BayesiaLab attempts to minimize the **MDL Score** by evaluating candidate networks during structural learning.

### Learn More About Calculating Complexity & Fit

{% content-ref url="calculating-complexity-dl-b.md" %}
[calculating-complexity-dl-b.md](calculating-complexity-dl-b.md)
{% endcontent-ref %}

{% content-ref url="calculating-fit-dl-d-or-b.md" %}
[calculating-fit-dl-d-or-b.md](calculating-fit-dl-d-or-b.md)
{% endcontent-ref %}
