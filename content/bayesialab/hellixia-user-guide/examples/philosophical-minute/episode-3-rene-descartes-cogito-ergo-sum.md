# Episode 3: René Descartes — Cogito Ergo Sum

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690035689/PM3_Descartes._001_kvdypj.png" alt=""><figcaption></figcaption></figure>

The third episode of our Philosophical Minute post is about the famous philosophical statement by René Descartes, Cogito Ergo Sum, "I think, therefore I am." This statement is at the core of Western philosophy and is the starting point of Descartes' philosophical methodology, the foundational element of his metaphysics.

Descartes sought a fundamental element that could be beyond any doubt as a basis for all knowledge. He posited that the very act of doubting one's own existence served as proof of the reality of one's own mind. In essence, if one is questioning, then one must exist to be able to do so.

> Considering that all the same thoughts that we have while awake can also come to us when we sleep, without any of them being true at that time, I resolved to pretend that all the things that had ever entered my mind were no more true than the illusions of my dreams.
>
> But immediately afterwards, I noticed that while I wanted to think that everything was false, it was necessary that I, who was thinking, be something; and realizing that this truth, I think, therefore I am, was so firm and so certain that even the most extravagant suppositions of skeptics were not capable of shaking it, I judged that I could accept it without hesitation as the first principle of the philosophy I was seeking.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690036484/Cogito_os3u8q.png" alt="" width="375"><figcaption></figcaption></figure>

### Workflow for Creating a Network of Keywords

* Start by creating a new node. Label this node "Descartes".
* Input the chosen excerpt of text into the comment section of the "Descartes" node.
* Run the **Dimension Elicitor**, set the **General Context** to "Philosophy", and input "Keywords" as the keyword for the analysis of the node comment.
* Examine the dimensions or keywords that Hellixia has identified. Any dimensions that appear irrelevant or redundant should be removed from your analysis.
* Use the **Embedding Generator** on all remaining nodes. This tool will quantify the semantics associated with the names and comments of each node.
* Set the "Descartes" node as your Target Node.&#x20;
* Run the **Naive Learning** algorithm.
* Update the visual style of all nodes to appear as "**Badges**". This will allow the comments within each node to be displayed.
* Switch to **Validation Mode**.
* Run an **Arc Force** analysis.
* Use the **Radial Layout** while you are still within the **Arc Force** analysis tool. This will arrange the nodes in a clockwise fashion based on the strength of their relationships with the target node.
* **Show the Arc Comments** to visualize information regarding the strength of the relationships between the nodes.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690384408/PM3-Descartes-KW_b5nirw.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for Creating a Semantic Network

* Start by copying the node "Descartes." Then, create a new graph and paste the node.&#x20;
* Utilize the **Dimension Elicitor** with the subsequent keywords: Arguments, Contents, Matters, Milestones, Rules, Themes, Theses, Topics, and the **General Context** set to "Philosophy."
* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Descartes" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network from the excerpt.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; note that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690384408/PM3-Descartes-SN_qlqt7o.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690384409/PM3-Descartes-NF_iz5czh.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690384408/PM3-Descartes-VC_lyco4s.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690384409/PM3-Descartes-HSN_frllap.svg" alt=""><figcaption></figcaption></figure>
