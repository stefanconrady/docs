# Causal DAGs

### Causal DAGs <a href="#h2_934734805" id="h2_934734805"></a>

We need to understand some important properties before encoding our causal knowledge in a DAG. We learned in [Chapter 2](../../chapter-2-bayesian-network-theory.md) that Bayesian networks use DAGs for the qualitative description of the [Joint Probability Distribution](../../../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md).

In the causal context, however, the arcs in a DAG explicitly state causality instead of only representing direct probabilistic dependencies in a Bayesian network. We now designate a DAG with a causal semantic as a Causal DAG (CDAG) to highlight this distinction.

### Structures Within a DAG <a href="#h3_818976540" id="h3_818976540"></a>

A DAG has three basic configurations in which nodes can be connected. Graphs of any size and complexity can be broken down into these basic graph structures. While these basic structures show direct dependencies/causes explicitly, there are more statements contained in them, albeit implicitly. In fact, we can read all marginal and conditional associations that exist between the nodes.

Why are we even interested in associations? Isn’t all this about understanding causal effects? It is essential to understand all associations in a system because, in non-experimental data, all we can do is observe associations, some of which represent non-causal relationships. Our objective is to identify causal effects from associations.

### **Indirect Connection**

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709674945/Chain_sm9uxa.svg" alt="" width="375"><figcaption></figcaption></figure>

This DAG represents an indirect connection of A on B via C.

* A Directed Arc represents a potential causal effect. The arc direction indicates the assumed causal direction, i.e., “A → C ” means “A causes C .”
* A Missing Arc encodes the definitive absence of a direct causal effect, i.e., no arc between A and B means no direct causal relationship exists between A and B and vice versa. As such, a missing arc represents an assumption.

**Implication for Causality**

A has a potential causal effect on B intermediated by C.

**Implication for Association**

Marginally (or unconditionally), A and B are dependent. This means that without knowing the exact value of C, learning about A informs us about B and vice versa, i.e., the path between the nodes is unblocked, and information can flow in both directions.

Conditionally on C, i.e., by setting Hard Evidence on (or observing) C, A, and B become independent. In other words, by “hard”-conditioning on C, we block the path from A to B and from B to A. Thus, A and B are conditionally independent, given C:

$$A\cancel{ \bot }B,A \bot B|C$$

{% hint style="warning" %}
Hard Evidence means that there is no uncertainty regarding the value of the observation or evidence. If uncertainty remains regarding the value of C, the path will not be entirely blocked, and an association will remain between A and B.
{% endhint %}

### **Common Parent**

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709687256/CommonParent_yjdwle.svg" alt="" width="375"><figcaption></figcaption></figure>

The second configuration has C as the common parent of A and B.\


**Implication for Causality**

C is the common cause of both A and B.

**Implication for Association**

In terms of association, this structure is absolutely equivalent to the Indirect Connection. Thus, A and B are marginally dependent but conditionally independent given C (by setting Hard Evidence on C):

$$A\cancel{ \bot }B,A \bot B|C$$

### **Common Child (Collider)**

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709760868/Collider_camdsx.svg" alt="" width="375"><figcaption></figcaption></figure>

The final structure has a common child C, with A and B being its parents. This structure is called a “V-Structure.” In this configuration, the common child C is also known as a “collider.”

**Implication for Causality**

A and B are the direct causes of C.

**Implication for Association**

Marginally (or unconditionally), A and B are independent, i.e., there is no information flow between A and B. Conditionally on C — with any kind of evidence — A and B become dependent. If we condition on the collider C, information can flow between A and B, i.e., conditioning on C opens the information flow between A and B:

$$A \bot B,A\cancel{ \bot }B|C$$

{% hint style="warning" %}
Even introducing a minor change in the distribution of C, e.g., from no observation (“color unknown”) to a very vague observation (“it could be anything, but it is probably not purple”), opens the information flow.
{% endhint %}

For purposes of formal reasoning, this type of connection is of special significance. Conditioning on C facilitates inter-causal reasoning, often referred to as the ability to “explain away” the other cause, given that the common effect is observed (see [Inter-Causal Reasoning in Chapter 4](../../chapter-4-knowledge-modeling-and-probabilistic-reasoning.md#inter-causal-reasoning)).

### Creating a CDAG Representing Simpson’s Paradox <a href="#h3_1022799991" id="h3_1022799991"></a>

To begin the encoding of our causal knowledge in the form of a CDAG, we draw three nodes, which represent X (Treatment), Y (Outcome), and Z (Gender). For now, we are only using the qualitative part of the network, i.e., we are not considering probabilities.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709761417/Simpson1_xysmzh.svg" alt="" width="375"><figcaption></figcaption></figure>

The absence of further nodes means that we assume that there are no additional variables in the Data-Generating Process (DGP), either observable or unobservable. Unfortunately, this is a very strong assumption that cannot be tested. We need to have a justification purely on theoretical grounds to make such an assumption.

In the next step, we must encode our causal assumptions regarding this domain. Given our background knowledge of this domain, we state that Z causes X and Y and that X causes Y.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709761633/Simpson_CDAG1_o0vdml.svg" alt="" width="188"><figcaption></figcaption></figure>

This means that we believe that gender is a cause of taking the treatment and has a causal effect on the outcome, too. We also assume that the treatment has a potential causal effect on the outcome.

Having accepted these causal assumptions, we now wish to identify the causal effect of X on Y. The question is whether this is possible on the basis of this causal graph and the available observational data for these three variables. Before we can answer this question, we need to think about what this CDAG specifically implies. Recall the types of structures that can exist in a DAG (see [Structures Within a DAG](causal-dags.md#h3\_818976540)). As it turns out, we can find all three of the basic structures in this example:

* Indirect Connection: Z causes Y via X
* Common Parent: Z causes X and Y
* Common Child: Z and X cause Y
