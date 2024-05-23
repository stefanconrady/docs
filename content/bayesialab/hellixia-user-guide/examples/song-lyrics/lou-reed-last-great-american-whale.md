# Lou Reed: Last Great American Whale

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690301752/Whale_tzover.png" alt="" width="375"><figcaption></figcaption></figure>

Join us as we plunge into the lyrical depths of "[Last Great American Whale](https://www.youtube.com/watch?v=ZEDxDrhzYJc\&ab\_channel=LouReed-Topic)", a song by the iconic musician Lou Reed. Known for his distinctive storytelling and unique blend of rock, this track from his 1989 album, 'New York', stands as a testament to Reed's keen observation of American society and culture.

In "Last Great American Whale", Reed weaves a tale that resonates with environmental and social commentary, a narrative that's as poignant today as it was when first penned. To navigate through this multifaceted piece of music, we'll be enlisting the aid of Hellixia, BayesiaLab's subject matter assistant.

Harnessing Hellixia's ability to create intricate semantic networks, we aim to dissect the themes, motifs, and narratives hidden within Reed's lyrics. This song, ripe with symbolism and metaphor, offers a rich landscape for such analysis.

From the overarching narratives of environmentalism and social critique to the individual threads of American culture, Hellixia will guide us through the complex lyrical world that Reed has created. So come, immerse yourself in the rhythm and the words, as we unravel the enigma of Lou Reed's 'Last Great American Whale'.

### Workflow for creating the Semantic Network

* Start by creating the node "Last Great American Whale". &#x20;
* Use the **Dimension Elicitor**, employing a broad array of keywords like "Developments", "Influencers", "Events", "Entities", and many more, to conduct an exhaustive analysis of the song lyrics (see the keywords that are listed in the **Class Editor** below).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690301901/LGAW-KW_osg4en.png" alt="" width="375"><figcaption></figcaption></figure>

* Inspect the dimensions returned by Hellixia and eliminate any that seem superfluous or unrelated to your analysis. Next, disregard the "Last Great American Whale" node and run the **Embedding Generator** on all remaining nodes to apprehend the semantic associations of their names and comments.
* Use the **Maximum Weight Spanning Tree** algorithm to generate a semantic network.&#x20;
* Change node styles to **Badges** to ensure each node's comment is visible. Then, apply the **Dynamic Grid Layout** to position the nodes on your graph; remember that this algorithm is not deterministic, and its orientation—vertical, horizontal, or mixed—is random. You might need to execute this layout several times to obtain an arrangement that aligns with your taste.
* Switch over to **Validation Mode** and select **Skeleton View**. Since your network doesn't represent causal relations, **Skeleton View** will maintain only node connections without indicating a direction.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690302602/LGAW-SN_pdttwq.svg" alt=""><figcaption></figcaption></figure>

</div>

### Workflow for Node Force Analysis

* Return to **Modeling Mode** and alter the node styles to **Discs**.&#x20;
* Use the **Symmetric Layout** and switch to **Validation Mode** to run a **Node Force** analysis.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690302603/LGAW-NF_i0uwub.svg" alt=""><figcaption></figcaption></figure>

### Workflow for Creating the Hierarchical Semantic Network

* Execute **Variable Clustering**: This operation will categorize analogous variables based on their semantic relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690302602/LGAW-VC_up03wl.svg" alt=""><figcaption></figcaption></figure>

* Open the **Class Editor** and run **Class Description Generator** to generate descriptive names for the factors in question. Use the **Export Descriptions** function, and save the newly created descriptions.
* Return to **Modeling Mode** and run **Multiple Clustering** to generate latent variables.&#x20;
* Run the structural learning algorithm **Taboo**. Ensure the "**Delete Unfixed Arcs**" option is enabled.
* Use the descriptions you exported earlier as a **Dictionary** to rename the latent variables you've created.
* Switch to **Validation** and apply **Node Force**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690302603/LGAW-HSN_mooicj.svg" alt=""><figcaption></figcaption></figure>

* Given the size of this network, we can focus on the upper level of the hierarchical network. Below is the Node Force analysis on these factors only, i.e., excluding all manifest variables before the analysis.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690302603/LGAW-HSN-L1_uzdksr.svg" alt=""><figcaption></figcaption></figure>
