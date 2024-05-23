# Thomas Hobbes: Leviathan (1651)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690288754/Leviathan_livre_zehazm.jpg" alt="" width="375"><figcaption></figcaption></figure>

Embarking on an exploration of one of the most influential works in the realm of political philosophy, we turn our attention to Thomas Hobbes' Leviathan. Penned in a time of civil strife, Leviathan serves as a cornerstone of Western political thought, offering insights into the nature of social contract, sovereignty, and the legitimacy of political power.

Hobbes' arguments and reasoning, profound yet intricate, necessitate a thoughtful and systematic approach to understanding. That is where Hellixia, BayesiaLab's subject matter assistant, comes into play. With the power to construct detailed semantic networks, Hellixia provides us with a uniquely comprehensive way to interpret and examine the depth of Leviathan.

Utilizing these semantic networks, we will delve into the complex themes and ideas that Hobbes presents, mapping out the interconnections and dissecting the concepts that lie at the heart of Leviathan. From the notions of the state of nature and the social contract to the role and extent of sovereignty, our journey through this foundational text, powered by Hellixia's semantic analysis, promises a fresh perspective and new insights into Hobbes' grand political treatise.

### Workflow for Creating a Semantic Network

* Start by creating the node "Leviathan". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Points", "Considerations", "Approaches", "Concepts", and many more, to conduct an exhaustive analysis of the book (see the keywords that are listed in the **Class Editor** below).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289486/Leviathan-KW_p7xopr.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Leviathan" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289383/Leviathan-SN_qwfzow.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289383/Leviathan-NF_b3oocj.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289383/Leviathan-VC_itwtnk.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289383/Leviathan-HSN_yddo0r.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the Node Force analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289383/Leviathan-HSN-L1_fjgpot.svg" alt=""><figcaption></figcaption></figure>
