# Tutorial: Creating a Semantic Network on Risk Analysis

In this tutorial, we employ Hellixia to explore the concept of "Risk Analysis" in all its facets.&#x20;

### Workflow

1. Hellixia retrieves an array of concepts related to risk analysis from ChatGPT and then generates a new node for each concept. Furthermore, Hellixia adds a descriptive comment to each node, as provided by ChatGPT.
2. Next, Hellixia generates embeddings based on the node names and comments. As a result, each node now features a vector of 1,536 numbers representing its semantic context.&#x20;
3. Using BayesiaLab's discretization function, each node's vector is binned into quintiles.
4. On this basis, an unsupervised learning algorithm, such as Maximum Weight Spanning Tree (MWST), learns a semantic network with the given nodes.
5. The new Dynamic Grid Layout can now arrange the network into an easily-readable format.
6. Running the Node Force Analysis, we see the strongest nodes and their connections in the network.

{% hint style="info" %}
#### Embeddings <a href="#embeddings" id="embeddings"></a>

In the context of machine learning and natural language processing (NLP), embedding refers to a mathematical representation of a word, phrase, sentence, or any other linguistic unit in a continuous vector space. Word embeddings, in particular, are widely used representations that capture the semantic and syntactic properties of words.
{% endhint %}

{% hint style="info" %}
#### Semantic Network

A semantic network is a graphical representation of knowledge or concepts organized in a network-like structure. It is a form of knowledge representation that depicts how different concepts or entities are related to each other through meaningful connections.

In a semantic network, concepts are represented as nodes, and their relationships are depicted as labeled links or arcs. These links indicate the connections or associations between the concepts, such as hierarchical, associative, or causal relationships.
{% endhint %}

### Hellixia Demo

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1687546583/RiskAnalysis_eoa44s.mp4" %}
