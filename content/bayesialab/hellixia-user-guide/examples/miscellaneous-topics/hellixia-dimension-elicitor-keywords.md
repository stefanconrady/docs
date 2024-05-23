# Hellixia Dimension Elicitor Keywords

### Context

In this section, we demonstrate how Hellixia can be utilized to form a semantic network from the 145 keywords provided by the **Dimension Elicitor**, illustrating the semantic connections between these keywords.

### Workflow for Creating the Semantic Network

* **Create Nodes**: create a node for each keyword by importing a CSV file where all the keywords are located on the first line, followed by a '0' on the second line and a '1' on the third line for each keyword. This structure will help BayesiaLab interpret these columns as variables.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690271676/KW-Import_ntsh4i.png" alt="" width="375"><figcaption></figcaption></figure>

* **Generate Embeddings**: Once you have created your nodes, select them all and use the **Embedding Generator**. This tool will capture the semantic meaning associated with the node names.
* **Learn Semantic Relationships**: Use the **Maximum Weight Spanning Tree** algorithm to learn the semantic relationships between these nodes (variables). This algorithm will create the most significant connections between the nodes, forming a tree structure that maximizes the total weight of the tree.
* **Automatic Node Positioning**: Apply the **Symmetric Layout** algorithm to the nodes for automatic positioning. This will organize your nodes in a visually clear and understandable way.
* Switch to **Validation Mode** and conduct a **Node Force Analysis**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690390912/Keyword-NF_oo7dyy.svg" alt=""><figcaption></figcaption></figure>



