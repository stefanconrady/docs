# Chapter 2: Bayesian Network Theory

_This chapter is based mainly on_ [_Pearl and Russell (2000)_](https://ftp.cs.ucla.edu/pub/stat\_ser/r277.pdf) _and was adapted with permission._

### History

**Probabilistic Graphical Models** based on **Directed Acyclic Graphs (DAG)** have a long and rich tradition, beginning with the work of geneticist Sewall Wright in the 1920s. Variants have appeared in many fields. Within statistics, such models are known as directed graphical models; within cognitive science and artificial intelligence, such models are known as Bayesian networks. The name honors the [Rev. Thomas Bayes](https://en.wikipedia.org/wiki/Thomas\_Bayes) (1702-1761), whose rule for updating probabilities in the light of new evidence is the foundation of the approach.

{% hint style="info" %}
Bayesian Networks are also known as Bayesian Belief Networks (BBN for short) or Bayes Nets. All these variations are entirely equivalent. However, in this book, we exclusively use the term Bayesian Network.
{% endhint %}

### Bayes' Theorem

Rev. Bayes addressed both the case of discrete probability distributions of data and the more complicated case of continuous probability distributions. In the discrete case, Bayes’ theorem relates the conditional and marginal probabilities of events $$A$$ and $$B$$, provided that the probability of $$B$$ is not equal to zero:

$$
P(A|B) = P(A) \times {{P(B|A)} \over {P(B)}}
$$

In Bayes’ theorem, each probability has a conventional name: $$P(A)$$ is the prior probability (or “unconditional” or “marginal” probability) of $$A$$. It is “prior” in the sense that it does not take into account any information about $$B$$; however, event $$B$$ need not occur after event $$A$$. In the nineteenth century, the unconditional probability$$P(A)$$in Bayes’ rule was called the “antecedent” probability; in deductive logic, the antecedent set of propositions and the inference rule imply consequences. [Sir Ronald A. Fisher](https://en.wikipedia.org/wiki/Ronald\_Fisher) called the unconditional probability $$P(A)$$ “a priori.”

$$P(A|B)$$ is the conditional probability of $$A$$, given $$B$$. It is also called the posterior probability because it is derived from or depends upon the specified value of $$B$$;

$${P(B|A)}$$ is the conditional probability of $$B$$ given $$A$$. It is also called the likelihood;

$${P(B)}$$ is the prior or marginal probability of $$B$$ and acts as a normalizing constant;

$${{P(B|A)} \over {P(B)}}$$ is the Bayes factor or likelihood ratio.

Bayes' theorem in this form represents how the conditional probability of event $$A$$ given $$B$$ is related to the converse conditional probability of $$B$$ given $$A$$.

### Motivation for Developing Bayesian Networks

The initial development of Bayesian networks in the late 1970s was motivated by the necessity of modeling top-down (semantic) and bottom-up (perceptual) combinations of evidence for inference. The capability for bidirectional inference, combined with a rigorous probabilistic foundation, led to the rapid emergence of Bayesian networks. They became the method of choice for uncertain reasoning in artificial intelligence and expert systems, replacing earlier, ad hoc rule-based schemes.

### Bayesian Network Elements

Bayesian networks are models that consist of two parts: a qualitative and a quantitive part.&#x20;

#### Qualitative Part

The qualitative part is a **Directed Acyclic Graph (DAG)** that specifies the dependencies between variables.

* Nodes represent variables of interest (e.g., the temperature of a device, the gender of a patient, a feature of an object, or the occurrence of an event). Such nodes can correspond to symbolic/categorical variables, numerical variables with discrete values, or discretized continuous variables.
* Directed arcs represent statistical (informational) or causal dependencies between the nodes. The directions are used to define "kinship" relations, i.e., parent-child relationships. For example, with an arc from $$X$$ to $$Y$$, $$X$$ is the parent node of $$Y$$, and $$Y$$ is the child node.

#### Quantitive Part

The quantitative part is based on local probability distributions for specifying the probabilistic relationships between nodes.&#x20;

The local probability distributions can be either marginal for nodes without parents (Root Nodes) or conditional for nodes with parents. In the latter case, the dependencies are quantified by [Conditional Probability Tables (CPT)](../key-concepts/conditional-probability-table-cpt.md) for each node given its parents in the graph.

Once fully specified, a Bayesian network compactly represents a [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) and, thus, can be used for computing the posterior probabilities of any subset of variables given evidence about any other subset.

### A Non-Causal Bayesian Network Example <a href="#h2__931841076221893932" id="h2__931841076221893932"></a>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267306/EyeHairColor_g8q0mj.svg" alt="" width="375"><figcaption></figcaption></figure>

The above illustration shows a simple Bayesian network consisting of only two nodes and one arc. It represents the [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) of the variables $$Eye\ Color$$ and $$Hair\ Color$$ in a population of students ([Snee, 1974](https://www.tandfonline.com/doi/abs/10.1080/00031305.1974.10479053)).&#x20;

In this case, the conditional probabilities of $$Hair\ Color$$, given the values of its parent node, $$Eye\ Color$$, are provided in a [Conditional Probability Table (CPT)](../key-concepts/conditional-probability-table-cpt.md). It is important to point out that this Bayesian network does not contain any causal assumptions, i.e., we do not know the causal order between the variables. Thus, the interpretation of this network should be merely statistical (informational).

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) EyeColorHairColor.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1687976329/EyeHairColor\_klye23.xbl)

### A Causal Network Example <a href="#h2__1716116530221893932" id="h2__1716116530221893932"></a>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267436/Sprinkler_yj8otp.svg" alt="" width="375"><figcaption></figcaption></figure>

The above graph illustrates another simple yet typical Bayesian network. In contrast to the statistical relationships in the non-causal example, this graph describes the causal relationships among the seasons of the year $$X_1$$, whether it is raining $$X_2$$, whether the sprinkler is on $$X_3$$, whether the pavement is wet $$X_4$$, and whether the pavement is slippery $$X_5$$. Here, the absence of a direct link between $$X_1$$ and $$X_5$$, for example, captures our understanding that there is no direct influence of season on slipperiness. The influence is mediated by the wetness of the pavement (if freezing were possible, a direct link could be added).

Perhaps the most important aspect of Bayesian networks is that they are direct representations of the world, not of reasoning processes. The arrows in the diagram represent real causal connections and not the flow of information during reasoning (as in rule-based systems and neural networks). Reasoning processes can operate on Bayesian networks by propagating information in any direction. For example, if the sprinkler is on, the pavement is probably wet (prediction, simulation). If someone slips on the pavement, that will also provide evidence that it is wet (abduction, reasoning to a probable cause, or diagnosis). On the other hand, if we see that the pavement is wet, that will make it more likely that the sprinkler is on or that it is raining (abduction); but if we then observe that the sprinkler is on, that will reduce the likelihood that it is raining (explaining away). It is the latter form of reasoning, explaining away, that is especially difficult to model in rule-based systems and neural networks in a natural way because it seems to require the propagation of information in two directions.

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) Sprinkler-Network.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1693315262/Sprinkler\_ebqzh8.xbl)

### A Dynamic Bayesian Network Example <a href="#h2_1538739112221893932" id="h2_1538739112221893932"></a>

Entities that live in a changing environment must keep track of variables whose values change over time.

Dynamic Bayesian networks capture this process by representing multiple copies of the state variables, one for each time step. A set of variables $$X_{t-1}$$ and $$X_{t}$$ denotes the world state at times $$t_{-1}$$and $$t$$, respectively. A set of evidence variables $$E_t$$ denotes the observations available at time $$t$$. The sensor model $$P(E_t|X_t)$$ is encoded in the conditional probability distributions for the observable variables, given the state variables. The transition model $$P(E_t|X_{t-1})$$ relates the state at time $$t_{-1}$$ to the state at time t. Keeping track of the world means computing the current probability distribution over world states given all past observations, i.e., $$P(X_t|E_1,...,E_t)$$.

Dynamic Bayesian networks (DBN) are a generalization of Hidden Markov Models (HMM) and Kalman Filters (KF). Every HMM and KF can be represented with a DBN. Furthermore, the DBN representation of an HMM is much more compact and, thus, much easier to understand. The nodes in the HMM represent the states of the system, whereas the nodes in the DBN represent the dimensions of the system. For example, the HMM representation of the valve system shown in the following graph is made of 26 nodes and 36 arcs versus 9 nodes and 11 arcs in the DBN ([Weber and Jouffe, 2003](https://hal.archives-ouvertes.fr/hal-00128475/document)).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267530/Valves_o6i4ur.svg" alt="" width="375"><figcaption></figcaption></figure>

### Representation of the Joint Probability Distribution <a href="#h2_1280512514221893932" id="h2_1280512514221893932"></a>

Any complete probabilistic model of a domain must — either explicitly or implicitly — represent the [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md), i.e., the probability of every possible event as defined by the combination of the values of all the variables.&#x20;

There are exponentially many such events, yet Bayesian networks achieve compactness by factoring the [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) into local, conditional distributions for each variable given its parents. If $$x_i$$ denotes some value of the variable $$X_i$$ and $$pa_i$$denotes some set of values for the parents of $$X_i$$, then $$P(x_i|pa_i)$$ denotes this conditional probability distribution.&#x20;

For example, in the graph below, $$P(x_4|x_2, x_3)$$is the probability of Wetness given the values of Sprinkler and Rain.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267647/SprinklerDescendants_xn8ak2.svg" alt="" width="375"><figcaption></figcaption></figure>

The global semantics of Bayesian networks specifies that the full [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md)  is given by the product rule (or chain rule):&#x20;

$$
P({x_i},...,{x_n}) = \prod\limits_i {P({x_i}|p{a_i})}
$$

In our example network, we have the following:

$$
P({x_1},{x_2},{x_3},{x_4},{x_5}) = P({x_1})P({x_2}|{x_1})P({x_3}|{x_1})P({x_4}|{x_2},{x_3})P({x_5}|{x_4})
$$

It becomes clear that the number of parameters grows linearly with the size of the network, i.e., the number of variables. In contrast, the size of the [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) itself grows exponentially. Given a discrete representation of the CPD with a [Conditional Probability Table (CPT)](../key-concepts/conditional-probability-table-cpt.md), the size of a local CPD grows exponentially with the number of parents. Savings can be achieved using compact CPD representations—such as noisy-OR models, trees, or neural networks.

The [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) representation with Bayesian networks also translates into local semantics, which asserts that each variable is independent of descendants in the network given its parents. For example, the parents of $$X_4$$ in the following graph are $$X_2$$ and $$X_3$$, and they render $$X_4$$ independent of the remaining non-descendant, $$X_1$$:

$$
P({x_4}|{x_1},{x_2},{x_3}) = P({x_4}|{x_2},{x_3})
$$

The collection of independence assertions formed in this way suffices to derive the global assertion of the product rule and vice versa. The local semantics is most useful for constructing Bayesian networks because selecting as parents all the direct causes (or direct relationships) of a given variable invariably satisfies the local conditional independence conditions. The global semantics leads directly to a variety of algorithms for reasoning.

### Evidential Reasoning <a href="#h2_213458965221893932" id="h2_213458965221893932"></a>

From the product rule, one can express the probability of any desired proposition in terms of the conditional probabilities specified in the network. For example, the probability that the Sprinkler is on given that the Pavement is slippery is:

$$
\begin{array}{l}
P({X_3} = on|{X_5} = true) = \frac{{P({X_3} = on,{X_5} = true)}}{{P({X_5} = true)}}\\
 = \frac{{\sum\nolimits_{{x_1},{x_2},{x_4}} {P({x_1},{x_2},{X_3} = on,{x_4},{X_5} = true)} }}{{\sum\nolimits_{{x_1},{x_2},{x_3},{x_4}} {P({x_1},{x_2},{x_3},{x_4},{X_5} = true)} }}\\
 = \frac{{\sum\nolimits_{{x_1},{x_2},{x_4}} {P({x_1})P({x_2}|{x_1})P({X_3} = on|{x_1})P({x_4}|{x_2},{X_3} = on)P({X_5} = true|{x_4})} }}{{\sum\nolimits_{{x_1},{x_2},{x_3},{x_4}} {P({x_1})P({x_2}|{x_1})P({x_3}|{x_1})P({x_4}|{x_2},{x_3})P({X_5} = true|{x_4})} }}
\end{array}
$$

These expressions can often be simplified in ways that reflect the structure of the network itself. The first algorithms proposed for probabilistic calculations in Bayesian networks used a local distributed message-passing architecture, typical of many cognitive activities. Initially, this approach was limited to tree-structured networks but was later extended to general networks in Lauritzen and Spiegelhalter’s (1988) method of junction tree propagation. A number of other exact methods have been developed and can be found in recent textbooks.

It is easy to show that reasoning in Bayesian networks subsumes the satisfiability problem in propositional logic and, therefore, exact inference is NP-hard. Monte Carlo simulation methods can be used for approximate inference (Pearl, 1988), giving gradually improving estimates as sampling proceeds. Unlike junction-tree methods, these methods use local message propagation on the original network structure. Alternatively, variational methods provide bounds on the true probability.

### Causal Reasoning <a href="#h2_1956943249221893932" id="h2_1956943249221893932"></a>

Most probabilistic models, including general Bayesian networks, describe a [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) over possible observed events but say nothing about what will happen if a certain intervention occurs. For example, what if I turn the Sprinkler on instead of just observing that it is turned on? What effect does that have on the Season or the connection between Wet and Slippery? A causal network, intuitively speaking, is a Bayesian network with the added property that the parents of each node are its direct causes. In such a network, the result of an intervention is obvious: the Sprinkler node is set to $$X_3=on$$, and the causal link between Season $$X_1$$ and the Sprinkler $$X_3$$ is removed. All other causal links and conditional probabilities remain intact, so the new model is:

$$P({x_1},{x_2},{x_3},{x_4}) = P({x_1})P({x_2}|{x_1})P({x_4}|{x_2},{X_3} = on)P({x_5}|{x_4})$$

Notice that this differs from observing that $$X_3=on$$ , which would result in a new model that included the term $$P(X_3=on|X_1)$$. This mirrors the difference between seeing and doing: after observing that the Sprinkler is on, we wish to infer that the Season is dry, that it probably did not rain, and so on. An arbitrary decision to turn on the Sprinkler should not result in any such beliefs.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267755/SprinklerIntervention_k3mnja.svg" alt="" width="375"><figcaption></figcaption></figure>

Causal networks are more properly defined, then, as Bayesian networks in which the correct probability model — after intervening to fix any node’s value — is given simply by deleting links from the node’s parents. For example, Fire → Smoke is a causal network, whereas Smoke → Fire is not, even though both networks are equally capable of representing any [Joint Probability Distribution (JPD)](../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) of the two variables.

Causal networks model the environment as a collection of stable component mechanisms. These mechanisms may be reconfigured locally by interventions, with corresponding local changes in the model. This, in turn, allows causal networks to be used very naturally for prediction by an agent that is considering various courses of action.

### Learning Bayesian Network Parameters <a href="#h2_882134650221893932" id="h2_882134650221893932"></a>

Given a qualitative Bayesian network structure, the conditional probability tables, $$P(x_i|pa_i)$$, are typically estimated with the maximum-likelihood approach from the observed frequencies in the dataset associated with the network.

In pure Bayesian approaches, Bayesian networks are designed from expert knowledge and include hyperparameter nodes. Data (usually scarce) is used as pieces of evidence for incrementally updating the distributions of the hyperparameters (Bayesian Updating).

### Learning Bayesian Network Structure <a href="#h2__1920162687221893932" id="h2__1920162687221893932"></a>

It is also possible to machine learn the structure of a Bayesian network, and two families of methods are available for that purpose. The first one, using constraint-based algorithms, is based on the probabilistic semantics of Bayesian networks. Links are added or deleted according to the results of statistical tests, which identify marginal and conditional independencies. The second approach, using score-based algorithms, is based on a metric that measures the quality of candidate networks with respect to the observed data. This metric trades off network complexity against the degree of fit to the data, which is typically expressed as the likelihood of the data given the network.

As a substrate for learning, Bayesian networks have the advantage that it is relatively easy to encode prior knowledge in network form by fixing portions of the structure, forbidding relations, or using prior distributions over the network parameters. Such prior knowledge can allow a system to learn accurate models from much less data than is required for clean sheet approaches.

### Causal Discovery <a href="#h2__158308457221893932" id="h2__158308457221893932"></a>

One of the most exciting prospects in recent years has been the possibility of using Bayesian networks to discover causal structures in raw statistical data—a task previously considered impossible without controlled experiments. Consider, for example, the following intransitive pattern of dependencies among three events: A and B are dependent, B and C are dependent, yet A and C are independent. If you asked a person to supply an example of three such events, the example would invariably portray A and C as two independent causes and B as their common effect, namely A → B ← C. For instance, A and C could be the outcomes of two fair coins, and B represents a bell that rings whenever either coin comes up heads.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1693267942/CoinTossBell_mxd3s1.svg" alt="" width="563"><figcaption></figcaption></figure>

Fitting this dependence pattern with a scenario where B is the cause and A and C are the effects is mathematically feasible but unnatural because it must entail fine-tuning the probabilities involved. The desired dependence pattern will be destroyed as soon as the probabilities change slightly.

Such thought experiments tell us that certain patterns of dependency, which are totally void of temporal information, are conceptually characteristic of certain causal directionalities and not others. When put together systematically, such patterns can be used to infer causal structures from raw data and to guarantee that any alternative structure compatible with the data must be less stable than the one(s) inferred; namely, slight fluctuations in parameters will render that structure incompatible with the data.

{% hint style="info" %}
Despite recent advances, causal discovery is an active research area with countless unresolved questions. Thus, no generally accepted causal discovery algorithms are currently available for applied researchers. As a result, all causal networks presented in this book are constructed from expert knowledge or machine learning and then validated as causal by experts. The assumptions necessary for a causal interpretation of a Bayesian network will be discussed in [Chapter 10](chapter-10-causal-effect-identification-and-estimation/).
{% endhint %}

