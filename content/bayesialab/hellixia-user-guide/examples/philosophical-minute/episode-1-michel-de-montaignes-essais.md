# Episode 1: Michel de Montaigne's Essais

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690036371/PM1_Montaigne._001_uvd7na.png" alt=""><figcaption></figcaption></figure>

Michel de Montaigne's "Essais" is a large collection (3 books) of many short subjective treatments of various topics published in 1580. Montaigne's stated design in writing, publishing, and revising the "Essais" over the period from approximately 1570 to 1592 was to record "some traits of \[his] character and of \[his] humours." The "Essais" were seen as an important work that established the essay as a recognized genre in literature. This work can be qualified as introspective philosophy.

Montaigne's "Essais" is not just a foundational work in the history of ideas; it's also a unique insight into the mind of one of the most curious and open thinkers in Western history. His observations on society, culture, and humanity are as relevant today as in the 16th century.

We are launching our 'Philosophical Minute' series with an excerpt from Book 2, 'Apology of Raimond de Sebonde'. We believe this passage serves as the perfect introduction to the series, as it refers to the profound wisdom of Socrates.

> The wisest man who ever lived, when asked what he knew, replied that he knew that he knew nothing. He confirmed what is said, that the greatest part of what we know is the least of what we do not know: that is to say, even what we think we know is a small part of our ignorance.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690014948/Montaigne1_oi0ybx.png" alt="" width="375"><figcaption></figcaption></figure>

### Workflow for Creating a Network of Keywords

* **Create a new node**: Start by creating a new node and label it as "Montaigne". This node will serve as a container for the text you want to analyze.
* **Enter the excerpt**: Input the selected text into the "Montaigne" node as a comment.
* Run the **Dimension Elicitor**, set the **General Context** to "Philosophy", and input "Keywords" as the keyword for the analysis of the node comment.
* **Review the dimensions**: Examine the dimensions or keywords returned by Hellixia. Remove any dimensions that seem redundant or irrelevant to your analysis.
* Use the **Embedding Generator** on all remaining nodes. This tool captures and quantifies the semantics associated with the names and comments of each node.
* **Set the target node**: Set "Montaigne" as the **Target Node**. The subsequent analyses and operations will focus on this node.
* Run the **Naive Learning** algorithm.&#x20;
* **Change node styles**: Alter the style of all nodes to "**Badges**". This style will display the comment within each node.
* Switch to **Validation Mode**.&#x20;
* Run the **Arc Force analysis**.&#x20;
* Apply the **Radial Layout**: While still in the **Arc Force** analysis tool, run the **Radial Layout.** This layout arranges the nodes in a clockwise manner according to the strength of their relationships with the target node.
* **Show the Arc Comments**: These comments will provide information about the strength of the relationships between nodes.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690379543/Hellixia_PM0_NaiveKW_tbqfcq.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating the Semantic Network

* Create a new node titled "Montaigne" that will contain the text we want to analyze.&#x20;
* Enter the excerpt as a comment within the "Montaigne" node.&#x20;
* Use the **Dimension Elicitor** with the **General Context** set to "Philosophy" and the keywords (Dimensions, Ideas, Themes, and Theses) to analyze the comment within your node. Review the dimensions that Hellixia returns, and remove any that appear to be redundant or irrelevant.
* Apply the **Embedding Generator** to all remaining nodes, capturing the semantics related to their names and comments.&#x20;
* **Exclude** the "Montaigne" node**.**
* Use the **Maximum Weight Spanning Tree** algorithm to create a semantic network that describes the analyzed text.&#x20;
* Change all node styles to **Badges** so that the comment within each node is displayed.&#x20;
* Apply the **Dynamic Grid Layout** to arrange the nodes.&#x20;
* Switch to **Validation Mode**.&#x20;
* Since the graph we're creating doesn't represent causal relationships, select the **Skeleton View** to remove any arc orientations.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690379543/Hellixia_PM0_SN_tfutis.svg" alt=""><figcaption></figcaption></figure>

### Workflow for the Node Force Analysis

* Switch back to **Modeling Mode.**
* **Exclude** the "Montaigne" node.&#x20;
* Change all node styles to the **Discs** format.&#x20;
* Enter **Validation Mode**.&#x20;
* Use the **Symmetric Layout.**
* Analyze the **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690379544/Hellixia_PM0_NF_ql63xt.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating the Hierarchical Semantic Network

* Run **Variable Clustering**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690379543/Hellixia_PM0_VC_lpbbxp.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and utilize the **Class Description Generator** to assign meaningful names to the three factors you're dealing with.
* Save these descriptions using the **Export Descriptions** feature.
* Switch back to **Modeling Mode**.&#x20;
* Execute **Multiple Clustering** to create latent variables.&#x20;
* Run **Taboo**, enabling the option **Delete Unfixed Arcs**, to create a hierarchical network.&#x20;
* Rename the latent variables you've just created by using the previously exported descriptions as a dictionary for naming the node names.
* Switch to **Validation Mode**.&#x20;
* Utilize the **Node Force** function.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690379544/Hellixia_PM0_HSN_upni3j.svg" alt=""><figcaption></figcaption></figure>



