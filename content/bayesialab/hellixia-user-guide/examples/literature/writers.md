# Writers

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690662938/Writers_c2gvsd.png" alt="" width="375"><figcaption></figcaption></figure>

Embark on a literary journey with us as we use Hellixia to uncover the rich interconnections among hundreds of authors, spanning a variety of literary styles such as magic realism, gothic fiction, surrealism, and science fiction. By mapping these intricate relationships, our semantic network becomes a personalized guide, helping you discover your next potential favorite read. This network is not just a visual tool, it's your passport to uncharted literary territories, ready to guide your reading adventure.

### Workflow for Creating the Semantic Network

* Start by creating the node "Magic Realism".&#x20;
* Utilize the **Dimension Elicitor** with  "Competitors" as the guiding keyword, setting the **General Context** to "Literature Style", to discover other literary styles.&#x20;
* Inspect the dimensions Hellixia generates and discard any that appear irrelevant or extraneous to your analysis.&#x20;
* Select all nodes.&#x20;
* Run the **Dimension Elicitor** again using "Members" as the keyword and "Influential Writers" as the **General Context**. This process aims to discover influential writers for each style, focusing on Node Comments as the **Main Subject of the Query**. Set the **Responses per Keyword** parameter to 20 to get a wide range of results.
* Inspect the resulting dimensions from Hellixia and remove any that appear irrelevant or superfluous.&#x20;
* Repeat the last 2 steps with the Node Names and Comments as **Main Subject of the Query**. This will enable the discovery of additional writers.
* Use the **Maximum Weight Spanning Tree** algorithm to create a semantic network.&#x20;
* Change node styles to Badges to display each node's comment.&#x20;
* Apply the **Dynamic Grid Layout** for positioning the nodes on your graph. This algorithm is not deterministic and favors vertical, horizontal, or mixed orientations randomly. Running this layout multiple times might be necessary until you achieve an arrangement that suits your preferences.&#x20;
* Switch to **Validation Mode** and activate **Skeleton View.** As your network does not represent causal relations, the Skeleton View will only show the connections between nodes without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690662516/Writers-SN_ui56pg.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for Node Force Analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690662516/Writers-NF_xqqvrl.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating a Distance Mapping

* Optional: **Delete all Arcs**. This can be helpful for achieving a cleaner graph layout.&#x20;
* Use the **Distance Mapping** algorithm based on **Mutual Information**. This algorithm creates a 2D layout where the nodes' distances are proportional to the semantic proximity between the nodes (considering both names and comments).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690662516/Writers_DM_h4qjqo.svg" alt=""><figcaption></figcaption></figure>

