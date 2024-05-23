# Delays in Scheduled Flight Departures

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706538223/FlightDelay_CNG_Simple_b6nprt.svg" alt="" width="375"><figcaption><p>Generated Causal Bayesian Network for Flight Delays Analysis<br>We conducted a 1-hour webinar on this topic. <a href="../../../../webinars-seminars-tutorials-examples-and-case-studies/webinar-discovering-complex-causal-structures-with-hellixia.md">Here is the recording for your reference</a>.</p></figcaption></figure>

In the complex and dynamic field of air transport, it is crucial for airlines to understand and mitigate flight delays. With the advent of sophisticated analytical tools like Hellixia, we now have the opportunity to delve deeper into the causal factors behind these delays. This article explores the innovative application of Hellixia in the creation of Causal Bayesian Networks (CBN), a method that transcends traditional data analysis to uncover the root causes of flight delays.

Using Hellixia for this purpose represents a significant advance in the field of causal analysis. By building causal Bayesian networks, we can map the complex web of factors contributing to delays, from weather conditions to logistical challenges.

In the following sections, we'll look at how Hellixia facilitates the construction of these causal networks, and the insights they provide into the management and prevention of flight delays.

First, we will perform a semantic analysis of the domain to obtain an overview of the key concepts and variables within the aircraft delay domain.

## Semantic and Hierarchical Semantic Networks

For our analysis of "Delays in scheduled flight departures", we start by building a semantic network, followed by a hierarchical semantic network, similar to our previous workflows (for example, as demonstrated with [Hamlet](../../literature/william-shakespeare-hamlet-1599-1601.md)). This process is essential for mapping the semantic landscape surrounding flight delays, providing a solid foundation for understanding the underlying dynamics of this issue.

* We begin our analysis by creating a node entitled "Delays in scheduled flight departures" and proceed to use **Hellixia's Dimension Elicitor**, using two distinct groups of keywords: '_**Ancestors**_' and '_**Descendants**_'. This approach allows us to explore in depth the factors leading to and resulting from flight delays.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706541720/FD-DI_bpfhxf.png" alt="" width="375"><figcaption><p>Dimension Elicitor Wizard</p></figcaption></figure>

* We carefully examine the dimensions provided by Hellixia, removing any that seem extraneous or irrelevant to our analysis. Next, we exclude 'Delays in scheduled flight departures' and run the **Embedding Generator** on the remaining nodes. This step is crucial to understanding the semantic relationships linked to their names and comments.
* We have two large sets of nodes: one representing "_**Ancestors**_" (42 nodes) and the other "_**Descendants**_" (69 nodes). Our approach is to learn a separate network for each group. To do this, we define specific constraints that prohibit relationships between nodes that do not belong to the same class.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706549607/FAE_ydba6f.png" alt="" width="375"><figcaption><p>Forbidden Arc Editor: Prevents relationships between nodes outside their Class (Ancestors and Descendants)</p></figcaption></figure>

* We then run the **Maximum Weight Spanning Tree** algorithm to find the most significant semantic relationships between nodes.
* To improve visibility, we change the node styles to **Badges**, clearly displaying the comment associated with node. Next, we run the **Dynamic Grid Layout** to position the nodes on the graph. It's important to note that this algorithm is not deterministic, resulting in random orientations - vertical, horizontal or mixed. As a result, we may have to apply this layout several times to get a configuration that matches your preferences.
* Next, we switch to **Validation Mode** and opt for the **Skeleton** **View**. In this context, since our network doesn't represent causal relationships, this view is particularly useful as it retains only the connections between nodes, omitting direction indicators.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706550406/SN2_Badges_aeio3w.svg" alt=""><figcaption><p>The two Semantic Networks: Ancestors (top) and Descendants (bottom)</p></figcaption></figure>

* Next, we run **Variable Clustering**. This step categorizes variables that are similar, grouping them based on the semantic relationships identified between them.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706551031/Ancestor_NF_VC_vn95s4.svg" alt=""><figcaption><p>Ancestors: Node Force Mapping with distinct color for each variable cluster</p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706551032/Descendant_NF_VC_gx1rew.svg" alt=""><figcaption><p>Descendants: Node Force Mapping with distinct color for each variable cluster</p></figcaption></figure>

We can now proceed with the creation of two hierarchical semantic networks.

* **Opening Class Editor**: We begin by accessing the **Class Editor** and then running the **Class Description Generator**. This generates descriptive names for the factors we're examining.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706551724/GenDesc_urrhgm.png" alt="" width="375"><figcaption><p>Generating Descriptions for each Class based on associated nodes</p></figcaption></figure>

* **Exporting Descriptions**: Next, we use the **Export Descriptions** function to save the newly created factor descriptions.
* **Returning to Modeling Mode**: We then switch back to **Modeling Mode** and conduct **Multiple Clustering** to create latent variables.
* **Running the Structural Learning Algorithm (Taboo)**: We run the **Taboo** algorithm for structural learning, ensuring that the **Delete Unfixed Arcs** option is selected.
* **Renaming Latent Variables with Exported Descriptions**: We utilize the descriptions we previously exported as a **Dictionary** to rename the latent variables, adding clarity to our model.
* **Switching to Validation Mode and Running Node Force**: Finally, we go back to **Validation Mode** and run the **Node Force** analysis, which helps us understand the dynamics and strength of the connections within our network.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706552335/Ancestor_HC_iot6vp.svg" alt=""><figcaption><p>Hierarchical Semantic Network of Ancestors</p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706552336/Descendant_HC_ocx3oz.svg" alt=""><figcaption><p>Hierarchical Semantic Network of Descendants</p></figcaption></figure>

## Causal Networks

Having established a global understanding of the domain via semantic networks, we're now ready to move forward with the construction of causal Bayesian networks, taking advantage of the latest capabilities introduced in Hellixia as part of BayesiaLab version 11.2.

### Low Complexity Causal Network Created Using the Causal Network Generator

We initiate the process by creating a node named **Delays in Scheduled Flight Departures** and then proceed to use the **Causal Network Generator** feature.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706623170/CNG_Small_c0ixpg.png" alt="" width="375"><figcaption><p>Causal Network Generator Wizard</p></figcaption></figure>

After one or two minutes, due to the complexity of the prompt, we manage to generate a small but fully specified causal Bayesian network (graph and probabilities). This network features directed arcs to signify causal relationships, with each arc accompanied by a succinct explanation of its causal link and an estimate of the effect, scaled from -100 (shown in red) to 100 (shown in blue).&#x20;

To differentiate nodes by depth using different colors, we first run the **Edit Class** function. Next, we select **Generate a Predefined Class - Depth**. Next, we select the four depth classes that have been created and apply the **Colors - Associate Random Colors with Classes** function to assign distinct colors to each class.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706623800/Small-CNG_ea8yr7.svg" alt=""><figcaption><p>Low Complexity Causal Bayesian Network. Node Colors Based on Depth. </p></figcaption></figure>

Nodes marked with an icon representing a function are parameterized using BayesiaLab's new **DualNoisyOr()** formula. This formula integrates both positive and negative interactions between Boolean variables (the causal effects returned by Hellixia).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706625266/DualNoisyOr_sazi49.png" alt=""><figcaption><p>DualNoisyOr() Utilized to Quantify Causal Relationships of 'Delays in Scheduled Flight Departures' with Its Four Parent Nodes</p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706625812/DualNoisyOr-CPT_todd3v.png" alt="" width="375"><figcaption><p>Conditional Probability Generated with the DualNoisyOr() of 'Delays in Scheduled Flight Departures'</p></figcaption></figure>

By selecting the **Create Corresponding Structural Priors** option in the **Causal Network Generator** wizard, we now have access to **Structural Priors**. The value of each prior is derived from the absolute value of the causal effect returned by Hellixia. In addition, the explanation provided for each prior corresponds to the description of its causal relationship. These structural priors can then be used later for network learning when relevant data becomes available.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706628129/StructuralPriors_iwimd3.png" alt=""><figcaption><p>Structural Priors</p></figcaption></figure>

To finalize this first causal network, we employ the **Hellixia Image Generator** to create unique icons for each node, based on the comment.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706627340/Dalle3_b3zd1f.png" alt="" width="188"><figcaption><p>Image Generator Wizard</p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706627546/Small-CNG-icons_v2lwib.svg" alt=""><figcaption><p>Low Complexity Causal Bayesian Network. Dall.E icons associated with each node</p></figcaption></figure>

### Higher Complexity Causal Network Created Using the Causal Network Generator

Let's move on to the creation of a more complex causal network by setting **Complexity** to **High**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706627788/CNG-FC_rx9jhp.png" alt="" width="375"><figcaption><p>Causal Network Generator Wizard</p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706629536/Large-CNG_izl2gn.svg" alt=""><figcaption><p>Large Causal Network</p></figcaption></figure>

The next crucial step is an in-depth examination of this automatically generated network. For example, we observe that **Fueling Delays** is identified as a direct cause. Interestingly, **Aircraft Turnaround Time** is also identified as a direct cause. This leads us to speculate that **Fueling Delays** could be a direct cause of **Aircraft Turnaround Time**, which would have an indirect effect on flight delays.

To verify this hypothesis, we select the two nodes, **Fueling Delays** and **Aircraft Turnaround Time**, and apply the Hellixia **Pairwise Causal Link** feature. This will help us ascertain the nature of the causal relationship between these variables.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706631176/FD-ATT_opdtot.svg" alt=""><figcaption><p>Causal Link between <strong>Fuel Efficiency</strong> and <strong>Aircraft Turnaround Time</strong></p></figcaption></figure>

Hellixia validates the existence of this causal relationship and accordingly updates the conditional probability distribution of **Aircraft Turnaround Time.** This update incorporates a **DualNoisyOr()** function with a coefficient of 0.75, reflecting the quantified impact of **Fueling Delays** on **Aircraft Turnaround Time.**

Following this update, our next step involves removing the direct link from **Fueling Delays** to **Delays in Scheduled Flight Departures.** Subsequently, we need to adjust the **DualNoisyOr()** formula to accurately reflect this change in the network's structure.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706631665/Large-CNG2_ocnned.svg" alt=""><figcaption><p><strong>Genetic Grid Layout Algorithm</strong> with a <strong>Bottom-Up Repartition</strong> approach</p></figcaption></figure>

Driven by curiosity to delve deeper, we select the relevant node to explore the causes of causes. For this, we once again make use of the **Causal Network Generator,**  but on **Fueling Delays.**

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706632430/CNG-FC2_xsekww.png" alt="" width="375"><figcaption><p>Low Complexity Network without Consequential Variables fro <strong>Fueling Delays</strong></p></figcaption></figure>

Upon reviewing the newly added nodes and relationships, we identified that three relationships were incorrectly marked as negative, contrary to the descriptions in their respective link comments. To rectify this, we change the color of these links to accurately reflect their positive nature and accordingly update the **DualNoisyOr()** formula of **Operational Efficiency**. &#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706633352/Large-CNG3_pxtogq.svg" alt=""><figcaption><p>Augmented Causal Network: Dash Links Indicate the Links that we have Corrected</p></figcaption></figure>

### Low Complexity Causal Network Created Using the Causal Relationships Finder

To conclude our analysis, we're going to build a final causal network, this time using the **Causal Relationships Finder** function. Unlike the **Causal Network Generator**, which added new nodes for creating the network, this feature works directly with selected nodes. To begin with, we use the **Dimension Elicitor** tool to identify the 5 main **Causes** and 5 main **Effects** associated with **Delays in Scheduled Flight Departures.**

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706635215/DI4CRF_x33cej.png" alt="" width="375"><figcaption><p>Dimension Elicitor Wizard to Get the Top 5 Causes and Effects of <strong>Delays in Scheduled Flight Departures</strong></p></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706635686/CRF0_vkjufi.svg" alt=""><figcaption><p>10 Causes and Effects created by the Dimension Elicitor</p></figcaption></figure>

We proceed by selecting the 10 causes and effects, along with the **Delays in Scheduled Flight Departures** node. With these nodes selected, we then run the Hellixia **Causal Relationships Finder** to create the network.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706635565/CRFWizard_huzoic.png" alt="" width="375"><figcaption><p>Causal Relationships Finder Wizard</p></figcaption></figure>

As a result, we obtain the bow-tie network structure below.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706635684/CRF1_kvkfv5.svg" alt=""><figcaption><p>Bow-tie Network Causal Network Generated with the Causal Relationships Finder</p></figcaption></figure>

This brings us to the end of our article. For further insights, we invite you to view the [recorded webinar on this topic, which was conducted in January 2024](../../../../webinars-seminars-tutorials-examples-and-case-studies/webinar-discovering-complex-causal-structures-with-hellixia.md).
