# Episode 8: Baruch Spinoza — The Ethics

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691575640/PM8-Spinoza._001_eqmn8j.png" alt=""><figcaption></figcaption></figure>

Welcome to the eighth installment of the Philosophical Minute, where we continue our exploration of the works of Baruch Spinoza. Today's focus is a captivating foray into Spinoza's reflections on desire, and its profound influence on our perceptions of good and evil:

> We consider good the thing that we desire; and consequently, we call the thing that inspires us with aversion, bad; so that everyone judges according to their passions what is good or bad, what is better or worse, what is most excellent or most contemptible.

Spinoza, in his meticulous examination, sheds light on the intrinsic nature of desire and its pivotal role in shaping human behavior and ethics. How does what we desire dictate our moral compass? Why do we perceive certain desires as virtuous and others as vice? Spinoza's insights into these questions offer a deep dive into the undercurrents of human psychology and the constructs of morality.

### Workflow for Creating a Network of Keywords

* Node Creation: Start by generating a new node. Name it "Spinoza".
* Text Inclusion: Insert your chosen text excerpt into the comment section of this "Spinoza" node.
* Dimension Elicitation: Use the **Dimension Elicitor** with the keyword "Keywords" to analyze the comment within the "Spinoza" node. Define the **General Context** as "Philosophy". This context directs the elicitor to frame the analysis within the broader realm of philosophical discourse.
* Dimension Review: Evaluate the dimensions or keywords identified by Hellixia. Remove any that seem redundant or not pertinent to your objective.
* Semantic Quantification: Run the **Embedding Generator** for all the nodes that are still in play. This process translates the semantic elements of each node's name and comments into quantifiable metrics.
* Target Node Designation: Designate "Spinoza" as your primary or **target** node.
* Learning Algorithm: Launch the **Naive Learning** algorithm.&#x20;
* Visualization: Alter the visual representation of every node to the "**Badges**" style. It ensures that the comments associated with each node are directly visible.
* Validation: Transition your workspace to the **Validation Mode**.
* Arc Analysis: Run the **Arc Force** analysis.&#x20;
* Graph Layout: While still in the **Arc Force** analysis tool, run the **Radial Layout**. This method organizes nodes in a circle around your target node, positioning them based on the strength of their connection to the target.
* Arc Visualization: Activate the **Arc Comments**. This feature superimposes a visualization layer on your network, displaying information about the arcs' strengths.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691581656/PM8-Spinoza-KW_atw6nn.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Semantic Network

* Start by copying the node "Spinoza". Then, create a new graph and paste the node.&#x20;
* Utilize the **Dimension Elicitor** with the subsequent keywords: Arguments, Ideas, Matters, Milestones, Motifs, Rules, Themes, and the **General Context** set to "Philosophy".
* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, exclude the "Spinoza" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network from the excerpt.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; bear in mind that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691581656/PM8-Spinoza-SN_kx30b5.svg" alt=""><figcaption></figcaption></figure>

### Workflow for the Node Force analysis

* Switch back to **Modeling Mode** and change the visual representation of each node to the "**Discs**" style. The disc style offers a clean and straightforward visual, which might be easier to interpret in some contexts compared to the badge style.
* Use the **Symmetric Layout** tool.&#x20;
* Switch to **Validation Mode** and run the **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691581656/PM8-Spinoza-NF_hznjli.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Carry out **Variable Clustering**: This action will group similar variables together based on their semantic connections.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691581656/PM8-Spinoza-VC_bojemv.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Switch back to **Modeling Mode** and run **Multiple Clustering** to produce latent variables.&#x20;
* Launch the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and run **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691581656/PM8-Spinoza-HSN_mcc9os.svg" alt=""><figcaption></figcaption></figure>
