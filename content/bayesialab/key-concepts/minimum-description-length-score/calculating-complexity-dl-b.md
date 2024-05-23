# Calculating Complexity: DL(B)

### Description Length of the Bayesian Network — DL(B)&#x20;

$$DL(B)$$ is the number of bits required to represent a Bayesian network. We can break down this value into the sum of two components:

* $$DL(G)$$, which stands for the number of bits required to represent the graph G of the Bayesian network,
* $$DL(P|G)$$ represents the number of bits required to represent the set of probability tables P.

$$DL(B) = DL(G) + DL(P|G)$$

#### Calculating DL(G)&#x20;

To calculate $$DL(G)$$, we need to determine the number of nodes and the number of their parent nodes.

$$DL(G) = \sum\limits_i^n {\left( {{{\log }_2}(n) + {{\log }_2}\left( {\begin{array}{*{20}{c}} n\\ {\left\| {P{a_i}} \right\|} \end{array}} \right)} \right)}$$

where

* n is the number of random variables (nodes): $${X_1},...,{X_n}$$
* $$P{a_i}$$ is the set of the random variables that are parents of $${X_i}$$ in graph G
* and $$P{a_i}$$ is the number of parents of the random variable $${X_i}$$.

#### Calculating DL(P|G)&#x20;

Computing $$DL(P|G)$$ is straightforward as it is proportional to the number of cells in all probability tables.

$$DL(P|G) = \sum\limits_i^n {\left( {\prod\limits_j^{\left\| {P{a_i}} \right\|} {{S_j} \times ({S_i} - 1) \times DL(p)} } \right)}$$

where

* $${{S}_{i}}$$ is the number of states of the random variable $${X_i}$$
* $$p$$ is the probability associated with the cell.

As the probability p cannot be known prior to learning the network, we use the following classical heuristic in BayesiaLab:

$$DL(p) = \frac{{{{\log }_2}(N)}}{2}$$
