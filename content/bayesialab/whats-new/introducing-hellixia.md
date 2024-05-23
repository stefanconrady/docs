# Introducing Hellixia

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690244836/Hellixia-Wordmark-1200x400_dseasm.png" alt=""><figcaption></figcaption></figure>

### Background & Motivation

To this day, no reliable methods exist to find causal relationships in data. More specifically, given a statistical association between two variables, it is impossible to establish which variable is the cause and which is the effect.

As a result, acquiring additional external information, such as human expert knowledge or the temporal order of the variables, has always been necessary to determine the causal direction in bivariate relationships.&#x20;

Given the importance of domain knowledge, the BayesiaLab team has developed new tools for expert knowledge elicitation for many years, such as the [Bayesia Expert Knowledge Elicitation Environment (BEKEE)](../../bekee/bayesia-expert-knowledge-elicitation-environment-bekee.md).&#x20;

Thus, the arrival of ChatGPT in 2022 has prompted the Bayesia team to immediately leverage the potential of Generative AI with BayesiaLab.

### Hellixia, BayesiaLab's New Subject Matter Assistant

Hellixia is the name of BayesiaLab's subject matter assistant powered by Generative AI. Hellixia offers a wide range of functions to help you characterize a given problem domain:

* Identify relevant dimensions of a problem domain
* Extract dimensions from a text
* Generate embeddings for learning a semantic network
* Generate meaningful descriptions for classes of nodes
* Provide tools for causal analysis
* Translate names and comments of nodes into different languages
* Generate images to be associated with nodes

{% hint style="info" %}
#### Embeddings <a href="#embeddings" id="embeddings"></a>

In the context of machine learning and natural language processing (NLP), embedding refers to a mathematical representation of a word, phrase, sentence, or any other linguistic unit in a continuous vector space. Word embeddings, in particular, are widely used representations that capture the semantic and syntactic properties of words.
{% endhint %}

{% hint style="info" %}
#### Semantic Network

A semantic network is a graphical representation of knowledge or concepts organized in a network-like structure. It is a form of knowledge representation that depicts how different concepts or entities are related to each other through meaningful connections.

In a semantic network, concepts are represented as nodes, and their relationships are depicted as labeled links or arcs. These links indicate the connections or associations between the concepts, such as hierarchical, associative, or causal relationships.
{% endhint %}

### Hellixia Workflow

A typical research workflow with Hellixia consists of the following steps:

* BayesiaLab utilizes its structural learning algorithms to find associations between variables.&#x20;
* Then, Hellixia obtains the causal directions for the learned associations and applies them as structural priors to the network.
* Finally, with these newly defined structural priors, BayesiaLab relearns the network. The final network now represents statistical knowledge from data plus the causal knowledge obtained from Large Language Models.

### Hellixia Performance

The [Tübingen Cause-Effect Pairs](https://webdav.tuebingen.mpg.de/cause-effect/) is a well-known dataset for assessing the performance of causal discovery methods. When tested against this dataset, Hellixia achieves 98% accuracy. The only errors are related to financial relationships for which Hellixia could not retrieve any causal relationships from ChatGPT.

The feature highlight of the BayesiaLab 11 is the integration of Hellixia, a subject matter assistant that leverages Generative AI for structural knowledge elicitation.

### Hellixia Preview at the 2023 BayesiaLab Spring Conference

In this presentation from the [2023 BayesiaLab Spring Conference](../bayesialab-conferences/2023-bayesialab-spring-conference/), we show the new Hellixia functions integrate GPT-4 directly into BayesiaLab, including:

* Chat Completion
* Image Generation
* Embedding Generation

As a result, the new Hellixia subject matter assistant can improve research workflows in several ways:

* Accelerate the qualitative part of knowledge elicitation.
* Generate practical natural language descriptions for latent factors created through BayesiaLab's clustering functions.
* Automatically create images to illustrate nodes in a network.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1686847598/BayesiaLab-Conferences/2023-Spring-Conference/Lionel-Jouffe/original_dauhab.mp4" %}

### Learn More

{% content-ref url="../hellixia-user-guide/" %}
[hellixia-user-guide](../hellixia-user-guide/)
{% endcontent-ref %}
