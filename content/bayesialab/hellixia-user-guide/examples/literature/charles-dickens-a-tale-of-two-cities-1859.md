# Charles Dickens: A Tale of Two Cities (1859)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690818913/Tales2Cities_iebsso.jpg" alt="" width="375"><figcaption></figcaption></figure>

Welcome to a deep dive into the depths of "A Tale of Two Cities," Charles Dickens' renowned novel that weaves a tapestry of intertwined lives against the backdrop of the French Revolution. With the help of Hellixia, we will create a detailed semantic network that exposes the complex relationships and themes embedded within this literary masterpiece. From its iconic characters and their motivations to the social and political currents driving the narrative, we'll explore the intricate layers that make this novel a timeless classic. Brace yourself for a journey through love, sacrifice, and redemption as we unravel Dickens' narrative in a way you've never seen before.

### Workflow for Creating the Semantic Network

* Start by creating the node "A Tale of Two Cities". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Agents", "Aspects", "Components", "Milestones", and many more, to conduct an exhaustive analysis of the book (see the exhaustive list of keywords below).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690797083/DickensKW_s1ime6.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "A Tale of Two Cities" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690812592/A_Tale_of_Two_Cities_SN_t96kl1.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690812592/A_Tale_of_Two_Cities_NF_uvgsjp.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690812591/A_Tale_of_Two_Cities_VC_q22gyd.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and run **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690812592/A_Tale_of_Two_Cities_HSN_eh3emm.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the **Node Force** analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690812837/A_Tale_of_Two_Cities_HSN-L1_k27xu4.svg" alt=""><figcaption></figcaption></figure>
