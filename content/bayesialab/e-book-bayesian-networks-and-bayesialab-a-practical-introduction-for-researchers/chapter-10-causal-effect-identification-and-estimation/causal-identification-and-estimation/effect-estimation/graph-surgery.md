# Graph Surgery

Let us summarize what we have so far: First, we have observational data from our domain. Second, we developed a theory about the DGP, i.e., the causal relationships in the domain. Both together will serve as the basis for estimating the causal effect. Before we do that, we should contemplate a very literal interpretation of these causal relationships.

If this causal graph is a correct representation of how the domain works, then every relationship between a pair of variables holds independently. Thus, the causal graph represents autonomous relationships between parent nodes and child nodes. It is as if each node were “listening for instructions” from its parents and only from its parents: the child node’s values are solely determined by the value of its parents, not of any other nodes in the system. Also, these relationships remain invariant regardless of any values that other nodes take on.

Let us now consider an outside intervention on X. Thus, rather than "listening" to its parent Z, X is now entirely determined by an external force and set to specific values, e.g., X=1 or X=0. This external intervention breaks the natural relationship between X and Z. Thus, Z no longer influences X. However, Z → Y and X → Y remain unaffected, and the original “natural” values of Z are not affected either.

What is the significance of all this? The idea is that intervening on X is like trying out, or simulating, what would happen if treatment were to be applied universally to the entire population — or withheld universally. Isn’t this the causal effect we are interested in? In other words, computing the causal effect is like simulating outside interventions on the treatment variable X.

How does this help us? By simulating an intervention, we “mutilate” the graph. This new graph looks like we had severed the arc going into the treatment variable X. This operation is what Judea Pearl has rather colorfully named “graph surgery” or “graph mutilation.”

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710190309/Simpson_CDAG5_d6wszo.svg" alt="" width="188"><figcaption></figcaption></figure>

Note that the mutilated graph achieves what was stipulated by the Adjustment Criterion: the non-causal path (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg)) X ← Z → Y does not exist any longer, as required by the Adjustment Criterion, and, given the autonomy of the other arcs, the causal path (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg)) X → Y remains unblocked.

Applying Graph Surgery allows us to transform a causal graph that represents a joint probability distribution P of observational data, i.e., pre-intervention distribution, into a new mutilated graph that represents the joint probability distribution Pm of the same variables under a simulated intervention, i.e., post-intervention distribution.

This new graph can tell us what happens to Y when we intervene and set X to a specific value, i.e., $$P(Y=y|do(X=x))$$. Note the do-operator! With this mutilated graph, we can compute the quantity of interest, the Average Causal Effect (ACE):

$$ACE = P\left( {Y = 1|do(X = 1)} \right) - P\left( {Y = 1|do(X = 0)} \right)\$$

where&#x20;

$$P(Y = y|do(X = x)) = {P_m}(Y = y|X = x)$$
