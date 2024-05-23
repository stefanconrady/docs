# Episode 7: Baruch Spinoza — The Ethics

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690220903/PM7-Spinoza._001_njvz3e.png" alt=""><figcaption></figcaption></figure>

Continuing with Baruch Spinoza's Ethics (see [Episode 6](episode-6-baruch-spinoza-the-ethics.md)), we focus on another passage about desire, determinism, and perceived free will in human actions.:

> All men are born in ignorance of causes, and a universal appetite of which they are conscious drives them to seek what is useful to them.
>
> A first consequence of this principle is that men believe they are free, because they are conscious of their volitions and desires, and do not think at all about the causes that predispose them to desire and to want.
>
> The result, secondly, is that men always act with an end in mind, namely, their own utility, the natural object of their desire.
>
> The supreme end of man, guided by reason, his supreme desire, this desire by which he strives to regulate all others, is therefore the desire that drives him to adequately understand both himself and all things that fall within his comprehension.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690220885/PM7-Spinoza_xjln1m.png" alt="" width="375"><figcaption></figcaption></figure>

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

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386758/PM7-Spinoza-NaiveKW_z3jrmy.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Semantic Network

* Start by copying the node "Spinoza". Then, create a new graph and paste the node.&#x20;
* Utilize the **Dimension Elicitor** with the subsequent keywords: Arguments, Ideas, Matters, Milestones, Motifs, Rules, Themes, and the **General Context** set to "Philosophy".
* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, exclude the "Spinoza" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network from the excerpt.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; bear in mind that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386757/PM7-Spinoza-SN_nqsalj.svg" alt=""><figcaption></figcaption></figure>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690386757/PM7-Spinoza-NF_juwh0o.svg" alt=""><figcaption></figcaption></figure>
