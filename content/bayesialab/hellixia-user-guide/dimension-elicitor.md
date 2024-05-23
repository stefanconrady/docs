# Dimension Elicitor

### Context

* The first step in formulating a new Bayesian network about a problem domain is typically defining the dimensions of that domain. This would also be the first step in the BEKEE workflow (see[bayesia-expert-knowledge-elicitation-environment-bekee.md](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md "mention"))
* Depending on the familiarity with the field of study, exploring a subject's facets and aspects may require a significant brainstorming effort. The Hellixia Dimension Elicitor assists by querying Large Language Models and proposing a list of dimensions.

### Usage & Example

* To illustrate the **Dimension Elicitor**, we want to discover the dimensions related to the concept of "Bayesian Belief Networks."
* Create a node representing the subject of interest, e.g., "Bayesian Belief Networks."
* Select `Toolbar > Node Creation Mode` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184129/BayesiaLab\_Icons/node\_glsrbu.svg)
* Move your pointer to the desired location to place your new node on the Graph Panel.
* Give the node a meaningful name representing the subject to be studied, i.e., "Bayesian Belief Networks."&#x20;
* You can also add a Long Name and a Node Comment to provide more information.
* Select the newly-created node, and then select `Main Menu > Hellixia > Dimension Elicitor`, which brings up the Dimension Elicitor Window.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689294573/Dimension-Elicitor-Window_tlkcjp.webp" alt="" width="375"><figcaption></figcaption></figure>

* In the Question Settings of the Dimension Elicitor Window, specify the keywords to be investigated. The list offers [145 keywords](examples/miscellaneous-topics/hellixia-dimension-elicitor-keywords.md) that Hellixia can use to query ChatGPT.&#x20;
* Select Advantages, Characteristics, Components, Contributions, Dimensions, and Strengths as **Keywords** to follow our example.
* **Responses per Keyword** specifies the maximum number of items to be retrieved per keyword.
* **Exclude Duplicates** automatically removes duplicates from the list of results. This is helpful as the query can produce identical **Dimensions** in the context of different **Keywords**.
* Depending on your OpenAI account and available resources, you can select the appropriate **Completion Model** from the dropdown menu, e.g., GPT-3.5 or GPT-4,&#x20;
* You can provide additional context by submitting a **Knowledge File**.&#x20;
  * This text file allows you to specify a broader context for a query.&#x20;
  * For example, you might embed chunks of documents related to your domain of study into a dataset.&#x20;
  * Then, you can identify and use the chunks with embeddings closest to that of your query to construct your Knowledge File.
* You can also provide a **General Context** for the query, e.g., "Artificial Intelligence."&#x20;
* The **Main Subject of the Query** is determined by the selected nodes.
  * You can use the **Node Name**, the **Node Long Name**, or the **Node Comments**.&#x20;
  * **Node Longe Names** and **Node Comments** have the advantage that they can include longer text and provide more information for the query.&#x20;
  * Both the **Node Long Names** and **Node Comments** are optional properties of a node. If they are selected as a **Main Subject for the Query** but have no content, Hellixia will use the **Node Name** by default.
* Click **Submit Query** to start the elicitation process.
* Once the query is complete, a table at the bottom of the window shows the results.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689294857/Dimension-Elicitation-Results-Table_bn5byq.webp" alt="" width="375"><figcaption></figcaption></figure>

* The **Subject Node** column displays the **Main Subject of the Query**.
* The **Keyword** column lists the keyword used for the dimension retrieved in that row.
* The **Index** column assigns an index to each dimension retrieved for a **Keyword**.
* The **Comment** column further describes the dimension retrieved. This comment will also be used as a **Node Comment**.
* The **Keep** column indicates which **Keyword/Dimensions** row to keep. If you checked **Exclude Duplicates**, only unique **Keyword/Dimension** combinations will be kept.
* However, you can modify the selection by checking and unchecking items in the **Keep** columns.
* All **Dimensions** are added as nodes to the **Graph Panel** upon clicking OK.
* If you select the option **Create a Class per Keyword**, the **Dimension** nodes are grouped by their associated **Keyword**. Additionally, a **Note** is added to visually group each set of nodes corresponding to a particular **Keyword/Dimension**.

<div data-full-width="false">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689296170/Dimension-Elicitor-Graph-Panel_nw6nz5.webp" alt=""><figcaption></figcaption></figure>

</div>

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689292391/Dimension-Elicitor_afhcyi.mp4" fullWidth="false" %}



