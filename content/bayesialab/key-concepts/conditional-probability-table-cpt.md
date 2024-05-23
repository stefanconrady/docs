# Conditional Probability Table (CPT)

### Context

* Bayesian networks are models that consist of two parts:
  1. A qualitative part to represent the dependencies using a Directed Acyclic Graph (DAG).
  2. A quantitative part, using local probability distributions, for specifying the probabilistic relationships.
* A Directed Acyclic Graph (DAG) consists of nodes and directed links:
  * Nodes represent variables of interest (e.g., the temperature of a device, the gender of a patient, a feature of an object, or the occurrence of an event).
  * Nodes can correspond to symbolic/categorical variables, numerical variables with discrete values, or discretized continuous variables.
  * Directed arcs represent statistical (informational) or causal dependencies among the variables. The directions are used to define kinship relations, i.e., parent-child relationships.
  * For example, in a Bayesian network with an arc from X to Y, X is the parent node of Y, and Y is the child node.
  * The local probability distributions can be either marginal for nodes without parents (Root Nodes) or conditional for nodes with parents.
  * In the latter case, the dependencies are quantified by Conditional Probability Tables (CPT) for each node given its parents in the Directed Acyclic Graph (DAG).
  * Once fully specified, a Bayesian network compactly represents the [Joint Probability Distribution (JPD)](joint-probability-and-joint-probability-distribution-jpd.md).
  * Thus, the Bayesian network can be used for computing the posterior probabilities of any subset of nodes given evidence set on any other subset.

### Example

* The following illustration shows a simple Bayesian network, which consists of only two nodes and one directed arc.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690479261/Eye-Hair-Color-Network_fip1hm.svg" alt="" width="375"><figcaption></figcaption></figure>

* This Bayesian network represents the [Joint Probability Distribution (JPD)](joint-probability-and-joint-probability-distribution-jpd.md) of the variables Eye Color and Hair Color in a population of students ([Snee, 1974](https://www.tandfonline.com/doi/abs/10.1080/00031305.1974.10479053)).
* Eye Color is a Root Node and, therefore, does not have any Parents. In other words, Eye Color does not depend on any other node.&#x20;
* As a result, the table associated with Eye Color is a Probability Table, i.e., it represents the marginal distribution of Eye Color unconditionally.&#x20;
* On the other hand, the probabilities of Hair Color are only defined conditionally upon the values of its parent node, Eye Color.
* Hence, the probabilities of Hair Color are provided in a Conditional Probability Table (CPT).
* It is important to point out that this Bayesian network does not imply any causal relationships, even though the arc direction may suggest that to a casual observer.&#x20;
* The arc direction merely defines the parent-child relationship of the nodes for purposes of representing the [Joint Probability Distribution (JPD)](joint-probability-and-joint-probability-distribution-jpd.md).
