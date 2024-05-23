# Episode 6: Baruch Spinoza — The Ethics

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690216746/PM6-Spinoza._001_pl7voi.png" alt=""><figcaption></figcaption></figure>

Baruch Spinoza's "Ethics" (often referred to as "Ethica" from its Latin title "Ethica, ordine geometrico demonstrata", meaning "Ethics Demonstrated in Geometrical Order") is a philosophical treatise written in the mid-17th century. It is one of the most significant and controversial works of the Enlightenment, and it presents Spinoza's metaphysical, epistemological, moral, and political views.

The structure of "Ethics" is unique: it is laid out like a geometrical treatise, akin to Euclid's "Elements". Starting with definitions and axioms, Spinoza proceeds with propositions, proofs, corollaries, and scholia (notes), aiming to demonstrate his philosophy with mathematical precision.

In this particular semantic analysis, we explore one of the famous quotes from Ethics:

> Desire is the very essence of man, insofar as it is conceived as determined to some action by any of its affections.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690216733/PM6-Spinoza_xsuzve.png" alt="" width="375"><figcaption></figcaption></figure>

### Workflow for Creating a Network of Keywords

* Start by creating a new node. Label this node "Spinoza".
* Input the chosen excerpt of text into the comment section of the "Spinoza" node.
* Use the keyword "Keywords" to guide the **Dimension Elicitor** in analyzing the comment in the "Spinoza" node. Specify the **General Context** for your analysis as "Philosophy". By setting this context, you are providing direction for the **Dimension Elicitor** to understand the broader topic of your text. The **Dimension Elicitor** will then identify and extract relevant dimensions or keywords from the comment.
* Examine the dimensions or keywords that Hellixia has identified. Any dimensions that appear irrelevant or redundant should be removed from your analysis.
* Use the **Embedding Generator** on all remaining nodes. This tool will quantify the semantics associated with the names and comments of each node.
* Set the "Spinoza" node as your Target Node.&#x20;
* Run the **Naive Learning** algorithm.
* Update the visual style of all nodes to appear as "**Badges**". This will allow the comments within each node to be displayed.
* Switch to **Validation Mode**.
* Run an **Arc Force** analysis.
* Use the **Radial Layout** while you are still within the **Arc Force** analysis tool. This will arrange the nodes in a clockwise fashion based on the strength of their relationships with the target node.
* **Show the Arc Comments** to visualize information regarding the strength of the relationships between the nodes.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386432/PM6-Sinpoza-NaiveKW_qxd0hw.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Semantic Network

* Start by copying the node "Spinoza". Then, create a new graph and paste the node.&#x20;
* Utilize the **Dimension Elicitor** with the subsequent keywords: Ideas, Rules, Themes, Theses,  Topics, and the **General Context** set to "Philosophy".
* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, exclude the "Spinoza" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network from the excerpt.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; bear in mind that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386432/PM6-Sinpoza-SN_msrn0c.svg" alt=""><figcaption></figcaption></figure>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386432/PM6-Sinpoza-NF_ybpijr.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386432/PM6-Sinpoza-VC_ew1mcd.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386433/PM6-Sinpoza-HSN_d5jijx.svg" alt=""><figcaption></figcaption></figure>
