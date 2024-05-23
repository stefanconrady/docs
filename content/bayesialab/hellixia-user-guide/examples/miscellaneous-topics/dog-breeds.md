# Dog Breeds

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690363354/DogBreeds_gjeufh.png" alt="" width="375"><figcaption></figcaption></figure>

Welcome to an engaging exploration of man's best friend, as seen through the lens of semantic networks. In this example, we will use the power of Hellixia to unravel the intricate web of relationships between different dog breeds.&#x20;

Whether you're a canine enthusiast, a professional breeder, or simply curious about the method, you'll find this demonstration enlightening and entertaining. Let's embark on this journey to better understand the world of dog breeds.

### Workflow for Creating a Semantic Network

* Create a node named "Dog Breeds".
* Use the **Dimension Elicitor,** and enter "Sample" as a single keyword to extract the 10 main breeds.
* Inspect the dimensions suggested by Hellixia. Any dimensions that are irrelevant or redundant should be removed from your analysis.
* Exclude the "Dog Breeds" node.
* Select the 10 created nodes.
* Open the **Dimension Elicitor** and enter "Competitors" as the keyword.&#x20;
* Set the **General Context** to "Dog Breeds". This ensures that the elicitor will only consider elements related to "Dog Breeds" during the analysis.
* Adjust the settings of the **Dimension Elicitor** to extract 10 breeds per node.&#x20;
* Run the **Dimension Elicitor** with the node name as the **Main Subject of the Query**.
* Review the results.  Any dimensions that are irrelevant or redundant should be removed from your analysis.
* Repeat the same workflow on the new nodes.
* Inspect the dimensions suggested by Hellixia. Any dimensions that are irrelevant or redundant should be removed from your analysis.
* Select all remaining nodes on your graph.
* Open the **Embedding Generator** tool: Set the **Linguistic Unit** to "Node Name" and "Node Comment": The linguistic unit refers to the part of the node that the Embedding Generator will use. In this case, it will analyze both the node names (i.e., the breeds of the dogs) and the node comments (i.e., the descriptions of the breeds).
* Run the **Embedding Generator.**
* Run the **Maximum Weight Spanning Tree** algorithm to create a semantic network.
* Change the style of all nodes to "**Badges**". This will display the comment within each node.
* Run the **Dynamic Grid Layout** to organize the nodes on your graph. Note that this algorithm's output is not deterministic; it may favor vertical, horizontal, or mixed orientations. Execute this layout multiple times until you find the most suitable arrangement.
* Switch to **Validation Mode**.
* As the graph you are building does not represent causal relationships, opt for the **Skeleton View**. This will remove all arc directions, leaving only the node connections without any specified direction.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690372401/DogBreeds-SN_ge56ic.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Node Force Analysis

* Switch back to **Modeling Mode**.
* Change all node styles to **Discs**.
* Use the **Symmetric Layou**t to organize your nodes in the graph.&#x20;
* Go to **Validation Mode.**
* Conduct a **Node Force** analysis to evaluate the strength of associations in your graph.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690372402/DogBreeds-NF_ofdf25.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating a Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690372401/DogBreeds-VC_owoobt.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690372402/DogBreeds-HSN_woq3ie.svg" alt=""><figcaption></figcaption></figure>
