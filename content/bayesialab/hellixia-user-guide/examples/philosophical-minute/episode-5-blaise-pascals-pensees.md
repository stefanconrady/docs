# Episode 5: Blaise Pascal's Pensées

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690212507/PM5_Pascal._001_p0f8ra.png" alt=""><figcaption></figcaption></figure>

In this fifth episode, we delve into another passage from Blaise Pascal's Pensées. This particular segment sheds light on the compromise required to uphold societal harmony, a state considered the highest form of good.

> Without doubt, the equality of goods is just; but, unable to make it force to obey justice, we have made it just to obey force; unable to strengthen justice, force was justified, so that the just and the strong might be together, and peace might be, which is the sovereign good.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690212534/PM5_Pascal_dvzknk.png" alt="" width="375"><figcaption></figcaption></figure>

### Workflow for Creating a Network of Keywords

* Create a new node: Start by generating a new node named "Blaise Pascal - Pensées". This node will hold the text that you plan to analyze.
* Insert the text: Add the selected excerpt into the comment section of the "Blaise Pascal - Pensées" node.
* Run the **Dimension Elicitor**, set the **General Context** to "Philosophy", and input "Keywords" as the keyword for the analysis of the node comment.
* Assess the extracted dimensions: Evaluate the keywords or dimensions identified by Hellixia and eliminate any that are redundant or irrelevant.
* Use the **Embedding Generator** for all remaining nodes. This tool will distill the semantics of the names and comments of each node into a quantifiable form.
* Set  "Blaise Pascal - Pensées" as the **Target Node**.
* Run the **Naive** Learning algorithm.
* Change the style of all nodes to "**Badges**". This style will display the comment embedded within each node.
* Switch to **Validation Mode**.
* Perform an **Arc Force** analysis.
* While within the **Arc Force** analysis tool, run the **Radial Layout**. This will arrange the nodes in a clockwise pattern in relation to their connection strength with the target node.
* **Show the Arc Comments**, which will provide information about the strength of the relationships between nodes.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690385974/PM5-Pascal-NaiveKW_fcb9d2.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for creating the Semantic Network

* Start by making a copy of the node named "Blaise Pascal - Pensées".
* Open a new graph and paste the copied "Blaise Pascal - Pensées" node.
* Use the following keywords to guide the **Dimension Elicitor** in its analysis of the node: Arguments, Contents, Ideas, Matters, Milestones, Motifs, Rules, Themes, Theses, Topics, and the **General Context** set to "Philosophy".
* Inspect the dimensions suggested by Hellixia. Any dimensions that are irrelevant or redundant should be removed from your analysis.
* Exclude the "Blaise Pascal - Pensées" node.
* Use the **Embedding Generator** on all remaining nodes.&#x20;
* Run the **Maximum Weight Spanning Tree** algorithm to create a semantic network based on the text analysis.
* Change the style of all nodes to "**Badges**". This will display the comment within each node.
* Run the **Dynamic Grid Layout** to organize the nodes on your graph. Note that this algorithm's output is not deterministic; it may favor vertical, horizontal, or mixed orientations. Execute this layout multiple times until you find the most suitable arrangement.
* Switch to **Validation Mode**.
* As the graph you are building does not represent causal relationships, opt for the **Skeleton View**. This will remove all arc directions, leaving only the node connections without any specified direction.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690385974/PM5-Pascal-SN_wrkfd9.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Node Force Analysis

* Switch back to **Modeling Mode**.
* Change all node styles to **Discs**.
* Use the **Symmetric Layou**t to organize your nodes in the graph.&#x20;
* Go to **Validation Mode.**
* Conduct a **Node Force** analysis to evaluate the strength of associations in your graph.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690385974/PM5-Pascal-NF_bzwjyo.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690385974/PM5-Pascal-VC_a8spr1.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor**.
* Run **Class Description Generator:** Use this function to generate descriptive names for your identified factors. This helps to make the output more understandable and interpretable.
* Save these descriptions by using the **Export Descriptions** function.&#x20;
* Switch back to **Modeling Mode**.
* Run **Multiple Clustering**.
* Run the **Taboo** algorithm: Use this structural learning algorithm to learn a hierarchical network. Make sure to enable the "**Delete Unfixed Arcs**" option to remove unnecessary connections and streamline your model.
* Use the descriptions you exported earlier as a dictionary to rename the latent variables you've just created. This helps in making your model more understandable and keeps the nodes' names consistent with their semantic meaning.
* Switch to **Validation Mode**.
* Apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690385975/PM5-Pascal-HSN_nphzc3.svg" alt=""><figcaption></figcaption></figure>

