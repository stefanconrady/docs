# What is a Bayesian Network?

### Overview&#x20;

* A Bayesian network, also known as a Bayesian belief network, is a probabilistic model representing a set of random variables and their conditional dependencies using a directed acyclic graph (DAG) and a set of conditional probability distributions.
* In a Bayesian network, each node in the DAG represents a random variable, and each directed arc represents a conditional dependency between the variables. The nodes in the network are associated with probability tables that specify the probability distribution of each variable given the values of its parent variables.
* Bayesian networks are used to model complex systems and make predictions based on incomplete or uncertain information. They can be used for various tasks, such as classification, prediction, diagnosis, decision-making, and causal reasoning.
* One of the critical advantages of Bayesian networks is that they allow for the efficient representation and computation of complex probability distributions. They are particularly useful when relationships between variables are complex and difficult to model using traditional statistical methods.
* Bayesian networks provide an elegant and sound approach to represent uncertainty and carry out rigorous probabilistic inference by propagating the pieces of evidence gathered on a subset of variables on the remaining variables.
* Bayesian networks are not only effective for representing experts’ beliefs, uncertain knowledge, and vague linguistic representations of knowledge via an intuitive graphical representation but are also powerful knowledge discovery tools when associated with machine learning and data mining techniques.

### Probabilistic Model&#x20;

From a technical point of view, a Bayesian network consists of two parts:

* Qualitative: a Directed Acyclic Graph (DAG), i.e., a special kind of directed graph that does not include cycles.
  * Directed Acyclic Graphs are composed of nodes that represent the variables of the domain (e.g., the temperature of a device, a feature of an object, the occurrence of an event, the age of a patient), and the links represent statistical (informational) or causal dependencies among the variables.
  * The DAG is the formal definition of the factorization of the [Joint Probability Distribution](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) over the set of all variables in the domain.
* Quantitative: conditional probability distributions to quantify the dependencies of each node given its parents in the DAG.

### Example&#x20;

Let’s take two variables: Age and Gray Hair. The corresponding DAG has two nodes, one for Age and another for Gray Hair.

As there is a probabilistic (and causal) relationship between Age and Gray Hair, there is a link between the two nodes:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693257335/GrayHairDAG_lohzjl.svg" alt=""><figcaption></figcaption></figure>

This graph defines a factorization of the joint probability distribution $$P(Age, Gray Hair)$$:

$$P(Age,Gray Hair) = P(Age) \times P(Gray Hair|Age)$$

#### Marginal Probability Distribution&#x20;

The probability distributions in a Bayesian network are typically represented with tables. The marginal distribution of the node Age is illustrated in the following table:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693257547/NodeAge_qc6aux.svg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693257819/AgeMarginalDistribution_xaoj11.svg" alt=""><figcaption></figcaption></figure>

This table tells us, for instance, that 16.4% of the population under study is less than 30 years old, while 9.4% is more than 70 years old.

#### Conditional Probability Table&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693257335/GrayHairDAG_lohzjl.svg" alt=""><figcaption></figcaption></figure>

The following Conditional Probability Table quantifies the relationship between Age and Gray Hair:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693257936/CPTAgeGrayHair_pdokfi.svg" alt=""><figcaption></figcaption></figure>

This suggests that among those under 30 years of age, 66% do not have any gray hair. Conversely, among people older than 70, 30.8% are completely gray.

### Probabilistic Inference&#x20;

* The DAG and the probability distributions associated with each node allow a compact representation of the [Joint Probability Distribution](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) over all the variables.
* Inference algorithms are available so that Bayesian networks can be used as probabilistic expert systems or inference engines for computing the posterior probability distributions of _unobserved_ nodes given evidence _observed_ on any number of _observed_ nodes.
* Also, observational inference in Bayesian networks is _omnidirectional_: it is possible to perform inference from parent nodes to child (simulation), child nodes to parent nodes (diagnosis), and any combination of the two kinds of inference.
* However, it is essential to point out that _causal_ inference can only be used in the context of simulation with a _causal_ Bayesian network.

#### Examples &#x20;

The following Monitors show the marginal probability distributions of Age and Gray Hair:\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/What-is-a-Bayesian-Network/MarginalDistributions.svg" alt=""><figcaption></figcaption></figure>

**Simulation Example**&#x20;

In this example, we simulate the posterior probability distribution of Gray Hair, given that we observe Age>70.

The top Monitor shows the observed evidence (Age>70); the bottom Monitor displays the posterior probability distribution of Gray Hair.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/What-is-a-Bayesian-Network/Age70.svg" alt=""><figcaption></figcaption></figure>

**Diagnosis Example**&#x20;

Now, we reason in the reverse direction. We observe Gray Hair=Moderate and infer (or diagnose) the posterior probability distribution of Age.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/What-is-a-Bayesian-Network/GrayHairModerate.svg)

### Bayesian Network Design&#x20;

There are two ways to create a Bayesian network:

* Knowledge Modeling: You can use any available expert knowledge to manually design a Bayesian network and define the corresponding probability distributions.
* Machine Learning: You can machine-learn a Bayesian network from data and estimate the corresponding probability distributions.&#x20;

Within the same theoretical framework, BayesiaLab offers a broad set of data mining algorithms:&#x20;

* Unsupervised Learning: BayesiaLab induces a Bayesian network to compactly represent the joint probability distribution sampled by the data set; all the variables have the same importance in this context.&#x20;
* Supervised Learning: BayesiaLab can learn a Bayesian network entirely focused on the characterization (or prediction) of a target variable.&#x20;
* Data Clustering: BayesiaLab creates a Bayesian network with a hidden variable to represent uniform groups of individuals/observations.&#x20;
* Variable Clustering: BayesiaLab identifies strongly connected variables that can be clustered into factors.&#x20;
* [Probabilistic Structural Equation Models](../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-8-probabilistic-structural-equation-models-for-key-driver-analysis/): BayesiaLab builds a hierarchical Bayesian network using hidden variables (or factors) that were identified during Variable Clustering.
