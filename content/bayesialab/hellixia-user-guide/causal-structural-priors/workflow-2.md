# Workflow 2

### Workflow Instructions

* In Workflow 1, we exported a Structural Prior Dictionary, including the Causal Structural Priors, and then imported this dictionary as an Arc Dictionary to create a causal network with these priors.
* In this Workflow 2, we will immediately utilize the Causal Structural Priors to machine-learning a new network without the export/import step.
* So, our starting point is the machine-learned network, for which Hellixia has already obtained the Causal Structural Priors. The Structural Prior icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103672/BayesiaLab-Logos/structural-priors\_mrkohy.svg) indicates that Structural Priors are associated with the network.
* However, these new Causal Structural Priors have not been used for updating the arc directions in the network.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689700019/Causal-Structural-Priors-Obtained_e5p1la.webp" alt=""><figcaption></figcaption></figure>

* Select `Main Menu > Learning > Unsupervised Structural Learning > Taboo`.

{% hint style="info" %}
Like Arc Constraints, Structural Priors, Temporal Indices, and Filtered States, Causal Structural Priors impose constraints on learning. As a result, EQ-based algorithms are not available under those conditions. &#x20;
{% endhint %}

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689686596/Associated-Arcs_dfkfvl.webp" alt=""><figcaption></figcaption></figure>

* This newly learned network now reflects the causal order obtained from ChatGPT.
* With the final arc directions in place, we should arrange the nodes into a more intuitive layout, i.e., positioning parent nodes above child nodes.
* Select `Main Menu > View > Layout > Genetic Grid Layout > Top-Down Repartition`.&#x20;
* Note that the algorithm keeps searching for a better layout until you stop the process by clicking the red button![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103679/BayesiaLab-Logos/red-button\_r825yi.svg)to the left of the Progress Bar.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689687276/Genetic-Grid-Layout-Progress-Bar_bf2the.webp" alt=""><figcaption></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689701630/Causal-Structural-Priors-Taboo-Learning_pqhsic.webp" alt=""><figcaption></figcaption></figure>

### Workflow Illustration



{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689703621/Workflow-2-Illustration_f08swn.mp4" %}
