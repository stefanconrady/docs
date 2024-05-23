# Chapter 8: Probabilistic Structural Equation Models for Key Driver Analysis

Structural Equation Modeling is a statistical technique for testing and estimating causal relations using a combination of statistical data and qualitative causal assumptions. This definition of a Structural Equation Model (SEM) was articulated by the geneticist Sewall Wright (1921), the economist Trygve Haavelmo (1943), and the cognitive scientist Herbert Simon (1953), and formally defined by Judea Pearl (2000). Structural Equation Models (SEM) allow both confirmatory and exploratory modeling, meaning they are suited to both theory testing and theory development.

What we call Probabilistic Structural Equation Models (PSEMs) in BayesiaLab are conceptually similar to traditional SEMs. However, PSEMs are based on a Bayesian network structure as opposed to a series of equations. More specifically, PSEMs can be distinguished from SEMs in terms of key characteristics:

In general, specifying and estimating a traditional SEM requires a high degree of statistical expertise. Additionally, the multitude of manual steps involved can make the entire SEM workflow extremely time-consuming. The PSEM workflow in BayesiaLab, on the other hand, is accessible to non-statistician subject matter experts. Perhaps more importantly, it can be faster by several orders of magnitude. Finally, once a PSEM is validated, it can be utilized like any other Bayesian network. This means that the full array of analysis, simulation, and optimization tools is available to leverage the knowledge represented in the PSEM.

### Example: Consumer Survey <a href="#h2_514559512" id="h2_514559512"></a>

In this chapter, we present a prototypical PSEM application: key drivers analysis and product optimization based on consumer survey data. We examine how consumers perceive product attributes and how these perceptions relate to the consumers’ purchase intent for specific products.

Given the inherent uncertainty of survey data, we also wish to identify higher-level variables, i.e., “latent” variables that represent concepts that are not directly measured in the survey. We do so by analyzing the relationships between the so-called “manifest” variables, i.e., variables that are directly measured in the survey. Including such concepts helps in building more stable and reliable models than what would be possible using manifest variables only.

Our overall objective is to make surveys clearer to interpret by researchers and make them “actionable” for decision-makers. The ultimate goal is to use the generated PSEM for prioritizing marketing and product initiatives to maximize purchase intent.

### Dataset <a href="#h2__128727182" id="h2__128727182"></a>

This study is based on a monadic consumer survey about perfumes, which was conducted by a market research agency in France. In this study, each respondent evaluated only one perfume.&#x20;

In this example, we use survey responses from 1,320 women who have evaluated a total of 11 fragrances (representative of the French market) on a wide range of attributes:

### Workflow Overview <a href="#h2_1157195842" id="h2_1157195842"></a>

A PSEM is a hierarchical Bayesian network that can be generated through a series of machine-learning and analysis tasks:

* All relationships in a PSEM are probabilistic—hence the name, as opposed to having deterministic relationships plus error terms in traditional SEMs.
* PSEMs are nonparametric, which facilitates the representation of nonlinear relationships plus relationships between categorical variables.
* The structure of PSEMs is partially or fully machine-learned from data.
  * 27 ratings on fragrance-related attributes, such as Sweet, Flowery, Feminine, etc., measured on a 1–10 scale.
  * 12 ratings with regard to imagery about someone who wears the respective fragrance, e.g. Sexy, Modern, measured on a 1–10 scale.
  * 1 variable for Intensity, a measure reflecting the level of intensity, measured on a 1–5 scale. The variable Intensity is listed separately due to the a priori knowledge of its non-linearity and the existence of a “just-about-right” level.
  * 1 variable for Purchase Intent, measured on a 1–6 scale.
  * 1 nominal variable, Product, for product identification.
* Unsupervised Learning to discover the strongest relationships between the manifest variables.
* Variable Clustering, based on the learned Bayesian network, to identify groups of variables that are strongly connected.
* Multiple Clustering: we consider the strong intra-cluster connections identified in the Variable Clustering step to be due to a “hidden common cause.” For each cluster of variables, we use Data Clustering—on the variables within the cluster only—to induce a latent variable representing the hidden cause.
* Unsupervised Learning to find the interrelations between the newly-created latent variables and their relationships with the Target Node.

### Workflow Details

{% content-ref url="data-import.md" %}
[data-import.md](data-import.md)
{% endcontent-ref %}

{% content-ref url="step-1-unsupervised-learning.md" %}
[step-1-unsupervised-learning.md](step-1-unsupervised-learning.md)
{% endcontent-ref %}

{% content-ref url="step-2-variable-clustering.md" %}
[step-2-variable-clustering.md](step-2-variable-clustering.md)
{% endcontent-ref %}

{% content-ref url="step-3-multiple-clustering.md" %}
[step-3-multiple-clustering.md](step-3-multiple-clustering.md)
{% endcontent-ref %}

{% content-ref url="step-4-completing-the-probabilistic-structural-equation-model.md" %}
[step-4-completing-the-probabilistic-structural-equation-model.md](step-4-completing-the-probabilistic-structural-equation-model.md)
{% endcontent-ref %}

{% content-ref url="key-driver-analysis.md" %}
[key-driver-analysis.md](key-driver-analysis.md)
{% endcontent-ref %}

{% content-ref url="product-optimization.md" %}
[product-optimization.md](product-optimization.md)
{% endcontent-ref %}
