# Workflow 1

### Workflow Instructions

* Clicking Export produces a so-called Structural Prior Dictionary, which is a text file containing all arc attributes, i.e.,
  * Start and End of arc
  * Structural Prior for each arc
  * Arc Comment, which, in this context, contains the Explanation for the causal directions as obtained from ChatGPT.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689620750/Structural-Priors-txt_cmnyv6.webp" alt=""><figcaption></figcaption></figure>

* We can now use this Structural Prior Dictionary as an Arc Dictionary and replace the original, machine-learned arcs with the ChatGPT-informed causal arcs.
* First, select `Graph Panel Contextual Menu > Delete All Arcs` to remove all existing arcs.
* Then, select `Main Menu > Data > Associate Dictionary > Arc >Arcs`.
* The network now features the causal arc directions as obtained from ChatGPT.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689686596/Associated-Arcs_dfkfvl.webp" alt=""><figcaption></figcaption></figure>

* With the final arc directions now in place, we should arrange the nodes into a more intuitive layout, i.e., positioning parent nodes above child nodes.
* Select `Main Menu > View > Layout > Genetic Grid Layout > Top-Down Repartition`.&#x20;
* Note that the algorithm keeps searching for a better layout until you stop the process by clicking the red button![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103679/BayesiaLab-Logos/red-button\_r825yi.svg)to the left of the Progress Bar.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689687276/Genetic-Grid-Layout-Progress-Bar_bf2the.webp" alt=""><figcaption></figcaption></figure>

* The network now displays the correct causal order of nodes and arcs.&#x20;
* Clicking the **Show Arc Comment** button ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103742/BayesiaLab-Logos/arc-comment\_zibiiq.svg) in the **Toolbar** displays the comments on the arcs. The Arc Comments show the explanations for the causal directions retrieved from ChatGPT.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689687838/Causal_Order-Arc-Comments_t9rfhu.webp" alt=""><figcaption></figcaption></figure>

### Workflow Illustration



{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689691895/Causal-Structural-Priors_sxhae8.mp4" %}
