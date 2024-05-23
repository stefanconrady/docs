# Philosophers

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690747899/Philosophers_xo1rgf.png" alt="" width="375"><figcaption></figcaption></figure>

In this section, we harness the power of Hellixia, crafting a temporal and causal semantic network to delve into the relationships between 25 philosophers across time. With the help of Hellixia Comment Generator, we construct a Temporal Indice Dictionary, enabling us to set temporal constraints.

### Workflow for Creating the Causal/Temporal Semantic Network

* Begin by creating a node named "Influential Philosophers".
* Utilize the **Dimension Elicitor** with "Samples" as **Keyword**. Adjust the **Responses per Keyword** setting to 25 to ensure a broad collection of answers.
* Review the dimensions returned by Hellixia, eliminating any that seem redundant or irrelevant to your analysis.
* Select all nodes.
* Run the **Comment Generator** with "Years" as the K**eyword**, setting the **Responses per Keyword** to 1, and checking the **Node Name** as the **Main Subject of the Query**. Set the **Output Settings** to **Dimension Name**. This step replaces the existing comments tied to the nodes with the primary date associated with each philosopher.
* Review the comments to ensure their accuracy. Modify BC dates to negative dates.
* Export the **Node Comments** as a **Dictionary** and associate it with **Node Temporal Indices**. These indices will be automatically used as structural constraints to orient the arcs from past to future.
* Select all nodes.
* Run the **Comment Generator** again, this time using "Field" as **Keyword** and "Philosophy" as  **General Context**. Set **Responses per Keyword** to 2, set the **Node Name** as the **Main Subject of the Query**, and set the **Output Settings** to **Dimension Name**. Make sure to check the box for **Append Output to Current Comment**. This action appends the current comments associated with the nodes with each philosopher's two main fields of study.
* Use the **Maximum Weight Spanning Tree** algorithm to construct the Causal/Temporal Semantic Network.
* Select all nodes and change the node styles to **Badges**, which allows the display of each node's comment.
* Run the **Genetic Grid Layout** algorithm to efficiently organize the nodes on your graph, reflecting the causal/temporal directionality of the connections.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690745813/Philosophers_CSN_hqzrxr.svg" alt=""><figcaption></figcaption></figure>
