# Node Force Interpretation

### Water Hose and Balloon Metaphor

To provide some intuition for the Arc Force and Node Force measures computed by BayesiaLab, we use the water hose and balloon metaphor:

Imagine that we have a Bayesian network in which the variables are balloons and the arcs are elastic, perforated water hoses. The size of the holes in the hose represents the uncertainty contained in the conditional probability table associated with the child node.

* For a deterministic relationship (i.e., we know the state of one variable given the state of the other one with certainty), there are no holes at all in the hose, and therefore, no water is lost between these two nodes.&#x20;
* Conversely, for an entirely uncertain relationship, in which information on one variable does not yield any information regarding the other one (such a “relationship” cannot be machine-learned as there is no correlation in the dataset), the size of the holes would be so large that no water could be transmitted from one node the other.

Now, we are sending a constant flow of water into this system. The thickness of a hose represents the actual water flow and is _inversely_ proportional to the size of its holes. Big holes mean that most water leaks, and the effective water flow is minimal.

The pressure in a balloon, and therefore its size, depends on the number of connected hoses and the sizes of their respective holes.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/attachments/2851018/2981962.png" alt="" width="563"><figcaption></figcaption></figure>

### Mapping Function

BayesiaLab's Mapping function visualizes Node Force and Arc Force so you can easily identify the most important variables in a network, even in high-dimensional spaces.&#x20;

In the networks below, for instance, the most important nodes are Country, Age, and Gender:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/attachments/2851018/2981963.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/FAQ/attachments/2851018/2981966.png" alt=""><figcaption></figcaption></figure>
