# Gustave Flaubert: Madame Bovary (1856)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690277964/MadameBovary_ory3cy.png" alt="" width="375"><figcaption></figcaption></figure>

"Madame Bovary" is a novel written by the French author Gustave Flaubert, published in 1857. It is one of the most influential literary works of the 19th century and is widely regarded as a seminal work of realism in literature. Flaubert's meticulous attention to detail and his pursuit of the "mot juste" (the exact right word) have made the novel a benchmark in the development of the modern novel.

Flaubert's portrayal of Emma Bovary is complex and multi-dimensional. While she can be seen as self-centered and even morally corrupt, she is also a victim of her environment, upbringing, and limited means of escaping her circumstances.

Semantic networks produced by Hellixia reveal the relationship between the characters and the structure of themes with unprecedented clarity.

### Workflow for Creating the Semantic Network

* Start by creating the node "Madame Bovary". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Agents", "Aspects", "Components", "Milestones", and many more, to conduct an exhaustive analysis of the book (see the keywords that are listed in the **Class Editor** below).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690289707/MadameBovary-KW_kmmhth.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Madame Bovary" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690300965/MadameBovary-SN_hncutx.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and change the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690279230/MadameBovary-NF_v3w1bw.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690279306/MadameBovary-VC_vfuyb2.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and run **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690279605/MadameBovary-HSN_wbo3tj.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the **Node Force** analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690280240/MadameBovary-HSN-L1_dym0nv.svg" alt=""><figcaption></figcaption></figure>

