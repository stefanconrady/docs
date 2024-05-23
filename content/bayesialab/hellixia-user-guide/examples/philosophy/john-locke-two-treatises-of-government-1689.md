# John Locke: Two Treatises of Government (1689)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692967150/JohnLocke_zozdtm.jpg" alt="" width="375"><figcaption></figcaption></figure>

Delve into the intricate world of John Locke's "Two Treatises of Government" in this dedicated section. Using the power of Hellixia, we aim to dissect this seminal work, which stands as a cornerstone of modern political philosophy. The text, rooted in the theories of natural rights and the social contract, has played a pivotal role in shaping democratic governance and individual liberties. Through our in-depth analysis, we will construct semantic networks that elucidate Locke's arguments, laying bare the foundational principles of his thoughts on society, governance, and the very nature of human rights. Join us on this enlightening journey as we navigate the depths of "Two Treatises," unraveling its philosophical intricacies and enduring relevance.

### Workflow for Creating a Semantic Network

* Start by creating the node "Two Treatises of Government, by John Locke". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Achievements", "Considerations", "Concepts", and many more, to conduct an exhaustive analysis of the essay (see the keywords that are listed in the **Class Editor** below).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692968599/KW_s1du56.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Two Treatises of Government, by John Locke" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692966619/2Treatises-SN_qhnoe8.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692966619/2Treatises-NF_ykl9pg.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692966619/2Treatises-VC_iimui6.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692966619/2Treatises-HNF_b34tzw.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the Node Force analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692966619/2Treatises-H1NF_rbksd5.svg" alt=""><figcaption></figcaption></figure>
