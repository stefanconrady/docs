# Deviance

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

* The **Deviance** measure is based on the difference between the [Entropy](entropy/) of the to-be-evaluated network $$B$$ and the [Entropy](entropy/) of the complete (i.e., fully connected) network $$C$$.&#x20;
* The closer the **Deviance** value is to 0, the better the network $$B$$ represents the dataset.

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

Deviance is formally defined as:

$${D_B} = 2N \times \ln (2) \times \left( {{H_B}({\cal D}) - {H_C}({\cal D})} \right)$$

where&#x20;

* $${{H_B}({\cal D})}$$ is the [Entropy](entropy/) of the dataset given the to-be-evaluated network $$B$$.
* $${{H_C}({\cal D})}$$ is the [Entropy](entropy/) of the dataset given the complete (i.e., fully connected) network $$C$$. In the complete network, all nodes are directly connected to all other nodes. Therefore, the complete network $$C$$ is an exact representation of the chain rule. As such, it does not utilize any conditional independence assumptions for representing the [Joint Probability Distribution](joint-probability-and-joint-probability-distribution-jpd.md).
* $$N$$ is the size of the dataset.
