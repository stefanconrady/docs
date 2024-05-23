# Inference: Diagnosis, Prediction, and Simulation

* The inherent ability of Bayesian networks to explicitly model uncertainty makes them suitable for a broad range of real-world applications.&#x20;
* In the Bayesian network framework, diagnosis, prediction, and simulation are identical computations. They all consist of observational inference conditional upon evidence:&#x20;
  * Inference from observed effects to causes: diagnosis or abduction.&#x20;
  * Inference from observed causes to effects: simulation or prediction.&#x20;
* This distinction, however, only exists from the perspective of the researcher, who would presumably see the symptom of a disease as the effect and the disease itself as the cause. Hence, carrying out inference based on observed symptoms is interpreted as a “diagnosis.”

### Observational Inference

* One of the central benefits of Bayesian networks is that they represent the Joint Probability Distribution and can therefore carry out inference “omnidirectionally.”
* Given an observation with any type of evidence on any of the networks’ nodes (or a subset of nodes), BayesiaLab computes the posterior probabilities of all other nodes in the network, regardless of arc directions.
* Both exact and approximate observational inference algorithms are implemented in BayesiaLab.

### Types of Evidence

* [Hard Evidence](https://www.bayesia.com/articles/bayesialab-knowledge-hub/7-unsupervised-learning/a/h3\_395350321): no uncertainty regarding the state of the variable (node).
* Likelihood/Virtual Evidence is defined by likelihoods associated with each variable state.
* [Probabilistic/Soft Evidence](https://www.bayesia.com/articles/bayesialab-knowledge-hub/7-unsupervised-learning), defined by marginal probability distributions.
* [Numerical Evidence](https://www.bayesia.com/articles/bayesialab-knowledge-hub/7-unsupervised-learning/a/h3\_1743203173), for numerical variables or for categorical/symbolic variables that have associated numerical values.

{% hint style="info" %}
See Examples & Learn More

* [Types of Evidence in Chapter 7: Unsupervised Learning](https://www.bayesia.com/articles/bayesialab-knowledge-hub/7-unsupervised-learning/a/h3\_395350321)
{% endhint %}

### Causal Inference

* Beyond observational inference, BayesiaLab can also perform causal inference for computing the impact of intervening on a subset of variables instead of merely observing these variables.
* Pearl’s Graph Surgery and Jouffe’s Likelihood Matching are available for this purpose.

{% hint style="info" %}
See Examples & Learn More

* [Chapter 10: Causal Effect Estimation](https://www.bayesia.com/articles/bayesialab-knowledge-hub/10-causal-effect-estimation)
* [Webinar: Media Mix Modeling and Optimization](https://www.bayesia.com/articles/bayesialab-knowledge-hub/media-mix-modeling-and-optimization)
{% endhint %}

### Effects Analysis

* Many research activities focus on estimating the size of an effect, e.g., to establish the treatment effect of a new drug or to determine the sales boost from a new advertising campaign. Other studies attempt to decompose observed effects into their causes, i.e., they perform attribution.
* BayesiaLab performs simulations to compute effects, as parameters as such do not exist in this nonparametric framework.
* As all the domain dynamics are encoded in discrete [Conditional Probability Tables (CPT)](https://www.bayesia.com/articles/bayesialab-knowledge-hub/key-concepts-conditional-probability-table), effect sizes only manifest themselves when different conditions are simulated.&#x20;
* [Total Effects Analysis](https://www.bayesia.com/articles/bayesialab-knowledge-hub/analysis-report-target-total-effects-on-target), [Target Mean Analysis](https://www.bayesia.com/articles/bayesialab-knowledge-hub/analysis-visual-target-target-posterior-curves-total-effects), and several other functions offer ways to study effects, including nonlinear and variable interactions.

{% hint style="info" %}
See Examples & Learn More

* [Total Effects and Direct Effects Calculation](https://www.bayesia.com/articles/bayesialab-knowledge-hub/total-effects-and-direct-effects-calculation-10092914)
* [Total Effects on Target vs Correlation with Target Node](https://www.bayesia.com/articles/bayesialab-knowledge-hub/total-effects-on-target-vs-correlation-with-target-node-3440971)
* [Webinar: What is Importance?](https://www.bayesia.com/articles/bayesialab-knowledge-hub/what-is-importance)
* [Webinar: Calculating Contributions Using Causal Counterfactuals](https://www.bayesia.com/articles/bayesialab-knowledge-hub/calculating-contributions-using-causal-counterfactuals)
{% endhint %}

### Optimization&#x20;

* BayesiaLab’s ability to perform inference over all possible states of all nodes in a network also provides the basis for searching for node values that optimize a target criterion. BayesiaLab’s [Target Optimization](https://www.bayesia.com/articles/bayesialab-knowledge-hub/analysis-target-optimization) is a set of tools for this purpose.
* Using these functions in combination with [Direct Effects](https://www.bayesia.com/articles/bayesialab-knowledge-hub/total-effects-and-direct-effects-calculation-10092914) is of particular interest when searching for the optimum combination of variables that have a nonlinear relationship with the target, plus co-relations between them.
* A typical example would be searching for the optimum mix of marketing expenditures to maximize sales. BayesiaLab’s [Genetic Target Optimization](https://www.bayesia.com/articles/bayesialab-knowledge-hub/analysis-target-optimization-genetic) will search, within the specified constraints, for those scenarios that optimize the target criterion.
