# Knowledge Modeling

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1687180316/HealthPolicyKnowledgeModeling_ha4jgc.png" alt=""><figcaption></figcaption></figure>

### Knowledge Modeling&#x20;

* Subject matter experts often express their causal understanding of a domain in the form of diagrams in which arrows indicate causal directions.
* This visual representation of causes and effects has a direct analog in the network graph in BayesiaLab.
* Nodes (representing variables) can be added and positioned on BayesiaLab’s [Graph Panel](https://www.bayesia.com/articles/bayesialab/graph-windows-graph-panel-usage) with a mouse click, and arcs (representing relationships) can be “drawn” between nodes.
* The causal direction can be encoded by orienting the arcs from cause to effect.
* The quantitative nature of relationships between variables, plus many other attributes, can be managed in BayesiaLab’s Node Editor.
* In this way, BayesiaLab facilitates the straightforward encoding of one’s understanding of a domain.
* Simultaneously, BayesiaLab enforces internal consistency so that impossible conditions cannot be encoded accidentally.

{% hint style="info" %}
See Examples & Learn More

* [Chapter 4: Knowledge Modeling & Probabilistic Reasoning](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-4-knowledge-modeling-and-probabilistic-reasoning.md)
* [Webinar: Reasoning About Renewable Energy](../webinars-seminars-tutorials-examples-and-case-studies/webinar-reasoning-about-energy-reliability-and-renewable-energy.md)
* Webinar: Optimizing Health Policies
{% endhint %}

### Knowledge Elicitation&#x20;

* In addition to directly encoding explicit knowledge in BayesiaLab, the [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md) is available to acquire the probabilities of a network from a group of experts.
* The [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md) is a web service that allows you to systematically elicit both explicit and tacit knowledge from multiple expert stakeholders.

{% hint style="info" %}
See Examples & Learn More

* [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md)
* [Seminar: Knowledge Elicitation & Geopolitical Reasoning Under Extreme Uncertainty with Bayesian Networks](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md)
* [Webinar: Differential Diagnosis of COVID-19](../webinars-seminars-tutorials-examples-and-case-studies/webinar-differential-diagnosis-of-covid-19.md)
{% endhint %}

### Discrete, Nonlinear, and Nonparametric Modeling&#x20;

* BayesiaLab contains all “parameters” describing probabilistic relationships between variables in [Conditional Probability Tables (CPT)](../key-concepts/conditional-probability-table-cpt.md), meaning no functional forms are utilized.
* Given this nonparametric, discrete approach, BayesiaLab can conveniently handle nonlinear relationships between variables. However, this [CPT](../key-concepts/conditional-probability-table-cpt.md)-based representation requires a preparation step for dealing with continuous variables, namely discretization. This consists of manually or automatically defining a discrete representation of all continuous values.
* BayesiaLab offers several tools for discretization, which are accessible in the [Data Import Wizard](../user-guide/main-menu/data/open-data-source-data-import-wizard/), in the Node Editor, and in a standalone Discretization function. Univariate, bivariate, and multivariate discretization algorithms are available in this context.
