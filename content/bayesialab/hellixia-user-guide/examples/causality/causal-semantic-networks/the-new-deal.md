# The New Deal

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690553807/New-Deal_bchtrn.png" alt="" width="375"><figcaption></figcaption></figure>

Join us as we delve into a detailed examination of the New Deal, an essential historical period shaped by the repercussions of the Great Depression. Triggered by our reading of John Steinbeck's poignant "The Grapes of Wrath," we will harness the power of Hellixia to create a  causal semantic network. This network will depict the policies enacted during the New Deal and explore their cause-and-effect relationships. Through this analysis, we aim to shed light on the complex interplay between economic conditions, policy decisions, and societal outcomes during this transformative era in American history.

### Workflow for Creating a Causal Semantic Network

* Create a node named "New Deal".
* Use the following keywords to guide the **Dimension Elicitor's** node analysis: Characteristics, Causes, Elements, Keywords, Features, Years, Dimensions, Definitions, Traits, Outcomes, Factors, Consequences, Aims, Descriptions, and Goals.
* Inspect the dimensions suggested by Hellixia. Any dimensions that are irrelevant or redundant should be removed from your analysis.
* Exclude the "New Deal" node.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Utilize Hellxia's **Causal Structural Priors** to evaluate whether the correlations highlighted by the maximum spanning tree indeed signify causal relationships.&#x20;
* Inspect the **Structural Priors Explanations** suggested by Hellixia. Any priors that are irrelevant should be removed.
* Run the **Taboo** **Learning** algorithm with the remaining **Structural Priors.** These priors will reduce the cost of adding arcs that embody these causal relations.&#x20;
* Use Hellxia's **Causal Structural Priors** again to examine if the highlighted correlations from the maximum spanning tree suggest causal relationships.&#x20;
* Repeat the above three steps as necessary until the model is satisfactory.&#x20;
* Inspect the final set of **Structural Priors Explanations** and remove any irrelevant priors.
* Export the **Structural Priors**.&#x20;
* Delete all arcs.&#x20;
* Use the saved **Structural Priors** as an arc dictionary. This will generate a causal network based on these priors.&#x20;
* Utilize the **Structural Priors** as an arc comment dictionary to store the descriptions of the causal relationships.&#x20;
* Apply the **Genetic Grid Layout** algorithm to neatly arrange the nodes on your graph, reflecting the causal directionality.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690561482/NewDeal-CSN_abld9i.svg" alt=""><figcaption></figcaption></figure>

The screenshot below displays the explanations associated with the Structural Priors. These explanations detail the causal relationships and the logical connections inferred by Hellixia's analysis between the different nodes in the network. They provide valuable insights into the underlying structure and dynamics of the system being studied.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690561488/NewDealSP_e5pzbn.png" alt=""><figcaption></figcaption></figure>

The blue icon in the 'Check' column signifies that an arc in the network currently represents the corresponding structural prior. If there's a red icon, it indicates that the arc is reversed. If there's no icon at all, it denotes the arc is absent from the network. The only red icon in the example below reflects that Hellixia identified a causal explanation in both directions.
