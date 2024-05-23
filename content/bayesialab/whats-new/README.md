---
description: Learn about the latest innovations in BayesiaLab 11
---

# 🆕 What's New?

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690246207/2023-Bayesialab-11-1200x400-v1-al-01_ugybbb.png" alt=""><figcaption></figcaption></figure>

## BayesiaLab 11

Version 11 of BayesiaLab is the latest iteration of our flagship product that has been under continuous development for nearly 25 years. No other organization has invested as many resources in developing technologies around the Bayesian network paradigm.

Release 11 once again features many innovations, including the native integration of a LLM-based subject matter assistant (OpenAI, OpenAI GPT Assistants, Azure, Mistral, ...).&#x20;

Here is a selection of the most important new features:

### Hellixia

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697643001/Hellixia_odt5w9.png" alt="" width="375"><figcaption></figcaption></figure>

**Hellixia** is the name of BayesiaLab's subject matter assistant based on Generative AI. Hellixia offers a wide range of functions to help you characterize a given problem domain:

* **Automatic Causal Network Generator:** This tool automatically creates a Causal Bayesian Network based on the user's input question. It generates nodes, adds detailed comments for each causal link explaining the mechanism, determines causal effects (with values ranging from -100 to 100), and constructs the conditional probability tables. The network is then automatically formatted.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1716299476/Rainbow_eib1uu.svg" alt="" width="188"><figcaption><p>Causal network automatically generated and formatted from the question: "Rainbow"</p></figcaption></figure>

* **Automatic Semantic Network Generator**: This tool automatically creates a Semantic Network to capture the main dimensions related to the user's input question.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1716303262/Rainbow_ASN_jc38js.svg" alt="" width="375"><figcaption><p>Semantic network automatically generated and formatted from the question: "Rainbow"</p></figcaption></figure>

* **Dimension Elicitor**: Identify relevant dimensions of a problem domain by using a large set of keywords and create the corresponding nodes.
* **Comment Generator**: Utilize a comprehensive set of keywords to pinpoint relevant dimensions within a problem domain and add them as comments to the nodes.
* **Embedding Generator**: This tool generates embeddings that capture the semantics of nodes using high-dimensional vectors, facilitating the learning of semantic networks.
* **Class Description Generator**: Generate descriptive summaries for a set of nodes. This tool is also integrated with the Multiple Clustering tool, enabling the automatic association of meaningful names with all latent variables.
* **Semantic Variable Clustering**: Create clusters of nodes based on their semantic.
* **Pairwise Causal Link**: This function evaluates the causal relationship between two nodes, adding an arc if a link exists. It also quantifies the causal effect (ranging from -100 to 100) and creates or updates the conditional probability table accordingly.
* **Causal Structural Priors**: This tool assesses the causal relationship between two nodes and creates a Structural Prior if a relationship exists. The value of the prior reflects the confidence level in the relationship's existence.
* **Causal Arc Explainer**: This tool examines the causal relationship between two nodes, providing a detailed description of the causal mechanism when a relationship is identified. Additionally, it quantifies the causal effect, with values ranging from -100 to 100.
* **Causal Network Generator**: This tool develops a Causal Bayesian Network focused on the chosen node. It generates new nodes, adds detailed comments for each causal link explaining the mechanism, determines causal effects (with values between -100 and 100), and constructs the conditional probability tables.
* **Causal Relationships Finder**: This tool, akin to the Causal Network Generator, is designed to build a causal network using a predefined set of nodes instead of centering around a single node and generating new nodes.
* **Image Generator:** This feature produces icons that visually represent the information linked to the nodes.
* **Translator**: This function translates various network elements — including names of nodes, states, and comments on nodes and arcs — into the chosen language.
* **Report Analyzer**: This tool processes the output from the _**Relationship Analysis Report**_, such as arc and node forces, and creates an HTML report that details the key dynamics of the domain represented by the network.

{% content-ref url="introducing-hellixia.md" %}
[introducing-hellixia.md](introducing-hellixia.md)
{% endcontent-ref %}

### Independence of Causal Influence

The Independence of Causal Influence (ICI) tool has been enhanced with several updates:

#### New Combination Functions

* `SumPos()`**:** An asymmetrical variation of the Sum function focusing on positive local mechanical effects.&#x20;
* `SumNeg()`**:** A counterpart that emphasizes negative local mechanical effects.&#x20;
* `MinMax()`: A function that implements the min method for negative values and the max method for positive ones.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1702907671/ICI_b05epq.png" alt="" width="375"><figcaption></figcaption></figure>

#### ICI Wizard Enhancement

* A **Condensed Display** option has been introduced. This feature creates a network where the local effects are snapped to their parent and the combination nodes to their respective children.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697474210/Wildfire_kr2mkq.svg" alt="" width="375"><figcaption></figcaption></figure>

### Expert Knowledge Elicitation-Related Features:

* The **Expert Editor** has been rebranded as the **SMEs & BEKEE Session Manager**.
* Subject Matter Experts (SMEs) can now be identified with specific colors for better differentiation.
* There's an option to decide whether to send out invitation emails to the SMEs.
* In terms of qualitative knowledge elicitation, specifically the qualitative segment of the Delphi Method, you can now utilize the **Assessment Editor** to produce **Notes** directly on the **Graph Panel**, derived from the comments provided by experts.\


<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697468127/BEKEE-Notes_qua2up.png" alt="" width="563"><figcaption></figcaption></figure>

* When eliciting a node, its current distribution can be dispatched as a prior to all experts in BEKEE, serving as an alternative to the default uniform distribution.
* **Node Contextual Menu**:
  * **Generate from Assessments:** this function facilitates the creation of distributions based on the weighted votes of chosen experts.
  * **Generate Assessments**: This feature uses the node's current probability distribution to create an assessment associated with a selected expert. When _**Prior Weights**_ are linked to the node, there's an option to use these weights to determine the expert's confidence level in the assessments.
  * **Delete Zero-Confidence Assessments**: this option removes all assessments in which the expert's confidence level is set to 0.
  * **Delete Assessments**: his feature deletes the assessments linked to the chosen experts.
* Hellinger Distance: Measures the distance between experts' votes and a reference expert (usually the consensus).&#x20;
* 2D/3D Mapping incorporates new metrics derived from experts' assessments.

### Formulas

The Formulas tab in the **Node Editor** now supports local variables.&#x20;

Additionally, new functions have been introduced, with some of the most notable being:

* `TriangularMD(v1, x)`, i.e., triangular membership degree in fuzzy logic (under **Special Functions**)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697475868/TriangularMD_o9j6hi.png" alt=""><figcaption><p>Local variable ($V) and TriangularMD function</p></figcaption></figure>

* `Deciban(x)`: The deciban is a logarithmic unit — much like the decibel or the Richter scale — introduced by Alan Turing for expressing probabilities. It is a tenth of a ban, which is also known as the base-10 log odds (under **Arithmetic Functions**)
* `Hellinger(v1, v2)`: The Hellinger distance is a measure of the similarity between two probability distributions (under **Inference Functions**)
* `NoisySum(s, leak, v1, w1, vn, wn):` Used for representing situations where the variable `s` is the weighted (`wi`) sum of its parents (`vi)` plus an additional noise term (`leak)` to model uncertainty or random fluctuations
* `DualNoisyOr(s, leak, c1, p1, cn, pn):` This function implements a modified Noisy-Or model that operates based on the combined effect of all `pi` values. The parameters `ci` represent conditions or boolean variables, while `pi` are their associated effects (positive or negative). When the aggregated sum of `pi` values is positive, the function executes a Noisy-Or with an overall effect equal to this sum, effectively determining the probability of the True state. Conversely, when the sum is negative, the function applies the Noisy-Or logic to the False state, adjusting the likelihood of the outcome being False according to this negative sum
* `SingleMode(v)`: A function designed to ascertain whether the distribution of variable _v_ is unimodal (under **Inference Functions**).&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697476861/SingleMode_ydfhou.png" alt="" width="375"><figcaption></figcaption></figure>

### Weight of Evidence

Weight of Evidence now features four new types of analyses:

* Most/Least Relevant Explanations
* Most/Least Confirmatory Clues

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1702907045/WoE_dmbe7j.png" alt="" width="375"><figcaption></figcaption></figure>

### Structural Learning Algorithms

The **EQ-based** learning algorithms are now disabled in scenarios where the score of an arc is not equivalent in both directions. This can occur due to filtered states, constraints, structural priors, etc. The assumption of equivalence is no longer theoretically valid in such contexts and could result in invalid networks with cycles.

### Evidence Scenario Files

* The data associated with the network can now be exported into an evidence scenario file.
* Scenarios are now editable, allowing adjustments to the index, weight, and comments.
* A new Evidence Scenario Report is now accessible, offering a detailed description of the scenarios' content.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1702909183/Evidence_xdshvz.png" alt="" width="375"><figcaption></figcaption></figure>

### Target Evaluation Tool

The redesigned **Target Evaluation** function now features dedicated tabs for:

* Classification
* Posterior Probabilities
* Regression
* Triage

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1702906713/TargetEvaluation_qijdev.png" alt="" width="375"><figcaption></figcaption></figure>

### Graph Layout, Rendering and Edition

* **Dynamic Grid Layout:** This innovative layout algorithm, particularly suitable for creating readable graphs featuring badges with associated comments, excels in handling graphs created with **Hellixia**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690246738/GridLayout_onya5n.svg" alt=""><figcaption></figcaption></figure>

* **View Menu:** four new functions have been introduced to optimize the display of graphs. Users can now shrink or stretch graphs both vertically and horizontally, offering enhanced visualization flexibility.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697646043/View_dfxmaw.png" alt="" width="188"><figcaption></figcaption></figure>

* **Position Menu**: this new item has been introduced to enable the adjustment of the graphical layers of Nodes and Notes. It's available via their contextual menus.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706353245/NodeLayer_q6ywsx.png" alt="" width="188"><figcaption></figcaption></figure>

* **Horizontal and Vertical Stacking**: These new alignment tools enable the positioning of the selected nodes horizontally or vertically, aligning them automatically closely without extra space.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706353979/Stacking_myitdx.svg" alt="" width="375"><figcaption></figcaption></figure>

* **Highlight a Class**: Accessible from the **Note Contextual Menu**, this feature lets you select a Class and then automatically adjusts the size and position of the note to encompass all nodes belonging to that class.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706354476/NoteClass_vvdh6f.svg" alt="" width="375"><figcaption></figcaption></figure>

* **Arc Editor**: Accessible by double-clicking an arc, this feature enables you to edit the text associated with the arc as well as its rendering properties.
* **Arc Comments**: The width, layer, and position of comments can now be modified. Additionally, an automatic layout algorithm is now available for positioning comments.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706354749/ArcComments_neop4p.svg" alt="" width="375"><figcaption></figcaption></figure>

* **Color Linked**: This new feature, added to the Rendering Properties of Badges, Monitors, Bars, and Gauges, automatically applies the node's associated color to the Name Background Color. Additionally, it also automatically selects white for the Name Color on dark backgrounds and black on lighter ones.
* By pressing '**Z**', a selection zone can be initiated, regardless of whether an object on the graph is clicked.
* **Numerical Evidence Entry for Gauges and Bars**: A new approach is introduced for inputting numerical evidence through shift-clicking on a node. Utilize the '**M**' and '**B**' icons to select the _**Distribution Estimation Method**_ (_MinXEnt_ and _Binary_, respectively), with the three icon colors representing the _**Observation Type**_: _No Fixing, Fix Mean_, and _Fix Probabilities_, respectively.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706359229/GaugeMeanValues_wvlngc.png" alt="" width="375"><figcaption></figcaption></figure>

* **Pseudo Root-Nodes**: If a node exclusively has _**Function Nodes**_ as parents, making it a root node of its subnetwork, and the parents of these _**Function Nodes**_ have fixed observed values, then the distribution of these pseudo root-nodes is also automatically set to fixed.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1706362838/PseudoRootNode_z3mn97.svg" alt="" width="375"><figcaption></figcaption></figure>

* **Boolean Conversion**: Featured in the **Tools** menu, this function enables the conversion of selected nodes into boolean nodes.

### 2D Mapping

* The **2D mapping** has been enhanced to incorporate an additional dimension for node analysis: **Font Size**, supplementing the existing **Node** **Size** and **Color** dimensions. This enables font sizes to be proportional to the selected metric.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1697647844/King_Lear_Holisitc_H1SN_fawukj.svg" alt=""><figcaption><p>Font Size proportional to Node Force</p></figcaption></figure>

* The **Node Analysis** section has been enriched with the addition of numerous metrics, providing a more comprehensive analysis capability:
  * Mutual Information with Target Node
  * Mutual Information with Target State
  * Bayes Factor
  * Normalized Bayes Factor
  * Kullback-Leibler
  * Normalized Kullback-Leibler
  * Total Effect on Target
  * Standardized Total Effect on Target
  * Direct Effect on Target
  * Standardized Direct Effect on Target
  * Number of Assessments
  * Assessment Completion Rate
  * Maximum Assessment Divergence
  * Overall Assessment Divergence
  * Missing Value Rate
* **Comments** associated with the nodes are now displayed when you hover over them.
* The option **Hide Text for Ignored Nodes** conceals the names of nodes that are not observable.

