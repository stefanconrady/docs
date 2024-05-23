# Causality Analysis

### Context

To this day, no reliable methods exist to find causal relationships in data. Given a statistical association between two variables, it is impossible, based on data alone, to establish which variable is the cause and which is the effect.

As a result, acquiring additional external information, such as human expert knowledge or the temporal order of the variables, remains necessary to determine the causal direction in bivariate relationships.&#x20;

With ChatGPT, it is now possible to let BayesiaLab tap into external domain knowledge. BayesiaLab's Hellixia can ask ChatGPT about the causal relationship between two nodes.&#x20;

### Usage & Example

* Select two nodes of interest, e.g., Smoking and Lung Cancer.
* Select `Main Menu > Hellixia > Causality Search`
* In the Causality Search Window:
  * Specify the Completion Model.
  * Provide any applicable context to the Context field.
  * Check which fields contain the subjects under study, e.g., Node Name, Node Long Name, and Node Comment.
* Click OK to launch the search.
* If ChatGPT believes a causal relationship exists, BayesiaLab adds a corresponding arc.
* Furthermore, BayesiaLab adds an **Arc Comment** with any contextual information ChatGPT provides. The **Arc Comment** icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) indicates that such a comment was added.&#x20;
* Clicking the **Show Arc Comment** button ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103742/BayesiaLab-Logos/arc-comment\_zibiiq.svg) in the **Toolbar** displays the comment.

### Workflow Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689190358/Causality-Search_uewwgm.mp4" %}





