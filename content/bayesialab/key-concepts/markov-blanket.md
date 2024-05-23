# Markov Blanket

* The **Markov Blanket** of node A is the set of nodes composed of A’s parents, its children, and its children’s other parents (i.e., spouses).
* The **Markov Blanket** of node A contains all the nodes that, if we know their states, i.e., we have hard evidence for these nodes, will make A independent of all other nodes.
* This means that the **Markov Blanket** of node A is the only knowledge needed to predict the posterior probability distribution of that node.
* Learning a **Markov Blanket** selects the most relevant predictor nodes, which is particularly helpful when there are many variables in a data set. As a result, this can serve as a highly efficient variable selection method.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690492939/110_atdy5n.webp" alt="" width="375"><figcaption></figcaption></figure>
