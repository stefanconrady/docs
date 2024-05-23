# Contingency Table Fit

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

**Contingency Table Fit (CTF)** measures the quality of the representation of the [Joint Probability Distribution](joint-probability-and-joint-probability-distribution-jpd.md) by a Bayesian network $$B$$ compared to a complete (i.e., fully-connected) network $$C$$.

BayesiaLab's **CTF** is defined as:

$$
{C_B} = 100 \times \frac{{{H_U}({\cal D}) - {H_B}({\cal D})}}{{{H_U}({\cal D}) - {H_C}({\cal D})}}
$$

where

* $${{H_U}({\cal D})}$$ is the entropy of the data with the unconnected network $$U$$.
* $${{H_B}({\cal D})}$$ is the entropy of the data with the evaluated network $$B$$.
* $${{H_C}({\cal D})}$$ is the entropy of the data with the complete (i.e., fully connected) network $$C$$. In the complete network, all nodes are directly connected to all other nodes. Therefore, the complete network $$C$$ is an exact representation of the chain rule. As such, it does not utilize any conditional independence assumptions for representing the [Joint Probability Distribution](joint-probability-and-joint-probability-distribution-jpd.md).&#x20;

### Interpretation <a href="#h2__1631879480" id="h2__1631879480"></a>

* $${C_B}$$ is equal to 100 if the [Joint Probability Distribution](joint-probability-and-joint-probability-distribution-jpd.md) is represented without any approximation, i.e., the entropy of the evaluated network $$B$$ is the same as that obtained with the complete network $$C$$.
* $${C_B}$$ is equal to 0 if the [Joint Probability Distribution](joint-probability-and-joint-probability-distribution-jpd.md) is represented by considering that all the variables are independent, i.e., the entropy of the evaluated network B is the same as the one obtained with the unconnected network $$U$$.
* $${C_B}$$ can also be negative if the parameters of network $$B$$ do not correspond to the dataset.
