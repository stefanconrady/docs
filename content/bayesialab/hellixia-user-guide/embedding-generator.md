# Embedding Generator

### Context <a href="#embeddings" id="embeddings"></a>

* In machine learning and Natural Language Processing (NLP), embedding is a mathematical representation of a token, word, phrase, sentence, or any other linguistic unit with a continuous high-dimensional vector. Word embeddings, in particular, are widely used representations that capture the semantic and syntactic properties of words.
* The embeddings used by Hellixia have 1,536 dimensions and allow capturing the semantics of the linguistic units defined by the nodes (names, long names, comments).

### Usage, Workflow, and Example

* To demonstrate the workflow for generating embeddings, we start with a set of 54 nodes representing a selection of influential 19th and 20th-century painters.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688334310/PaintersXBL_xqtota.webp" alt=""><figcaption></figcaption></figure>

* In Modeling Mode ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103779/BayesiaLab-Logos/Modeling-Mode-Icon\_dhvfvj.svg), select the nodes on the Graph Panel for which you want to generate embeddings. In our example, we select all 54 nodes.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688334443/PaintersSelected_wm0tpt.webp" alt=""><figcaption></figcaption></figure>

* Go to `Main Menu > Hellixia > Embedding Generator`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688334552/PaintersEmbeddingGenerator_ftfyeg.webp" alt=""><figcaption></figcaption></figure>

* Select one or more Input Types from the Hellixia Embedding Generator Window, i.e., Node Name, Node Long Name, and Node Comment. In the example, only Node Names are defined, so that is the only Input Type you need to select.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688334740/PaintersEmbeddingGeneratorWindow_mupr9o.webp" alt=""><figcaption></figcaption></figure>

* Click OK.
* Upon retrieving the embeddings, the Main Window shows the database icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103707/BayesiaLab-Logos/database\_xjs8hv.svg) in the bottom right corner. This indicates that the embeddings are now attached as a dataset.
* Each node now has 1,536 observations, which is indicated by the Tooltip associated with the database icon.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688336148/PaintersWithEmbeddings_mgd9hy.webp" alt=""><figcaption></figcaption></figure>

* By default, the observations associated with each node are discretized into quintiles, which you can see by switching into Validation Mode ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103664/BayesiaLab-Logos/validation\_e8r3qb.svg) and bringing up any of the Monitors.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688336852/PaintersMonitorPanel_di6s10.webp" alt=""><figcaption></figcaption></figure>

### Application Example: Learning a Semantic Network

{% hint style="info" %}
#### Semantic Network

A semantic network is a graphical representation of knowledge or concepts organized in a network-like structure. It is a form of knowledge representation that depicts how different concepts or entities are related to each other through meaningful connections.

In a semantic network, concepts are represented as nodes, and their relationships are depicted as labeled links or arcs. These links indicate the connections or associations between the concepts, such as hierarchical, associative, or causal relationships.
{% endhint %}

* With the embeddings now stored as observations, we can machine-learn a semantic network.
* For this purpose, we use one of BayesiaLab's Unsupervised Learning algorithms.
* The Maximum Weight Spanning Tree (MWST) is the best choice in this context. The algorithm is quick and renders an easily interpretable network.
* From the Modeling Mode ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103779/BayesiaLab-Logos/Modeling-Mode-Icon\_dhvfvj.svg), select `Main Menu > Learning > Unsupervised Structural Learning > Maximum Spanning Tree`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688348352/PaintersMWST_tnvyp5.webp" alt=""><figcaption></figcaption></figure>

* After the learning is completed, the resulting network appears in the following screenshot:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688348496/PaintersMWST2_pxhumn.webp" alt=""><figcaption></figcaption></figure>

* We can apply one of BayesiaLab's layout algorithms to interpret this graph more easily.&#x20;
* For instance, select `Main Menu > View > Layout > Symmetric Layout`.
* The resulting graph is shown outside the BayesiaLab window so that its structure can be viewed and interpreted more easily.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1688349116/PaintersSymmetricLayout_yreohd.webp" alt=""><figcaption></figcaption></figure>

</div>



### Workflow Illustrations

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689276065/Embedding-Generator_yercdk.mp4" %}

### Related Materials & Networks

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td>Painters.xbl</td><td></td><td></td><td><a href="../../.gitbook/assets/PaintersXBL.webp">PaintersXBL.webp</a></td><td><a href="https://res.cloudinary.com/dvr3obmlj/raw/upload/v1688333313/Painters_tgtirm.xbl">https://res.cloudinary.com/dvr3obmlj/raw/upload/v1688333313/Painters_tgtirm.xbl</a></td></tr></tbody></table>

