# Once Upon a Time in America (1984)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691156151/Once_Upon_a_Time_in_America_Sergio_Leone_ohuizs.png" alt="" width="375"><figcaption></figcaption></figure>

Welcome to our exploration of Sergio Leone's epic masterpiece, "Once Upon a Time in America." Spanning decades, this cinematic tour de force weaves a complex tale of friendship, ambition, betrayal, and redemption against the backdrop of organized crime in 20th-century America.

Leone's storytelling prowess, coupled with a haunting score by Ennio Morricone and remarkable performances by a stellar cast, including Robert De Niro and James Woods, make this film an unforgettable journey through time and human emotion.

From the gritty streets of New York's Lower East Side to the lavish elegance of 1960s' Manhattan, "Once Upon a Time in America" unfolds its narrative with a richness and complexity rarely seen in cinema. The film's non-linear structure, exquisite cinematography, and deeply layered themes make it an object of fascination and study.

Join us as we delve into this magnum opus, unraveling its intricate narrative threads and uncovering the symbolism, motifs, and philosophical undertones that elevate this movie to the status of timeless art. Whether you're revisiting this classic or discovering it for the first time, our analysis promises to provide new insights into a film that continues to captivate audiences worldwide.

### Workflow for Creating the Semantic Network

* Start by creating the node "Once Upon a Time in America". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Achievements", "Characteristics", "Components", "Milestones", and many more, to conduct an exhaustive analysis of the book (see the exhaustive list of keywords below). Set the **General Context** to "Sergio Leone Movie".

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690823820/ApocalypseNowKW_adv3hp.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Once Upon a Time in America" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691154974/Once_Upon_a_Time_in_America_SN_zualk5.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for the Node Force analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691154974/Once_Upon_a_Time_in_America_NF_qevkfs.svg" alt=""><figcaption></figcaption></figure>

### Workflow for creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691154974/Once_Upon_a_Time_in_America_VC_tiudlj.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and run **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691154975/Once_Upon_a_Time_in_America_HSN_ie85m9.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the **Node Force** analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691154974/Once_Upon_a_Time_in_America_HSN-L1_lvmih2.svg" alt=""><figcaption></figcaption></figure>
