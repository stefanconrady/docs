# Comment Generator

### Context

* Hellixia's **Comment Generator** is similar to the [Dimension Elicitor](dimension-elicitor.md).
* In the case of the [Dimension Elicitor](dimension-elicitor.md), Hellixia creates new nodes.
* With the Comment Generator, Hellixia retrieves Dimension Names and the related Comments from ChatGPT and adds them automatically to the Node Comment.

### Usage & Example

* Create a node representing the subject of interest, e.g., "Judea Pearl."
* Select `Toolbar > Node Creation Mode` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184129/BayesiaLab\_Icons/node\_glsrbu.svg)
* Move your pointer to the desired location to place your new node on the **Graph Panel**.
* Give the node a meaningful name representing the subject to be studied, i.e., "Judea Pearl."&#x20;
* You can also add a **Node Long Name** and a **Node Comment** to provide more information.
* Select the newly-created node, and then select `Main Menu > Hellixia > Comment Generator`, which brings up the **Comment Generator** window.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689377955/Comment-Generator-Window_egbo5j.webp" alt="" width="375"><figcaption></figcaption></figure>

* There is a range of settings you need to specify in the Comment Generator window:
  * Under **Question Settings**,&#x20;
    * Specify the **Keyword** from the dropdown menu.
    * If needed, stipulate the maximum number of responses per **Keyword**.
    * Select the **Completion Model** from the dropdown menu, e.g., GPT\_35 or GPT\_4.
  * Under **Context**,
    * Open a **Knowledge File**, if available.
    * Provide a **General Context** for the query. In our example, use "Artificial Intelligence."
  * Under **Main Subject of the Query**, select all fields that contain relevant information for the query, i.e., **Node Name**, **Node Long Name**, and **Node Comment**. Check all that apply. Both the **Node Long Names** and **Node Comments** are optional properties. If they're selected but not defined for a given node, Hellixia will use the **Node Name** by default.
  * Click **Submit Query**, and Hellixia retrieves the responses from ChatGPT and lists them in a table at the bottom of the **Comment Generator** window.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689378697/Comment-Generator-Window-Results-2_qpnef4.webp" alt="" width="563"><figcaption></figcaption></figure>

* The **Subject Node** column displays the main subject of the query.
* The **Keyword** column lists the keyword used for the **Dimension** retrieved in that row.
* The **Index** column assigns an index to each **Dimension** retrieved for a **Keyword**.
* The **Comment** column further describes the **Dimension** retrieved.
* The **Keep** column indicates which **Keyword/Dimensions** row to keep.&#x20;
* Under **Output Settings**, specify what part of the results table will be added to the **Node Comment**.
* Checking **Dimension Name and Comment** and **Concatenate Output to Current Comment**, you will obtain a **Comment** like this, which you can see in the **Node Editor**.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689379046/Comment-Generator-Node-Comment_qz2r1t.webp" alt="" width="563"><figcaption></figcaption></figure>

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689380419/Comment-Generator_gtxnfk.mp4" %}
