# Overview of Book

### Preface&#x20;

While Bayesian networks have flourished in academia over the past three decades, their application for research has developed more slowly. One reason has been the sheer difficulty of generating Bayesian networks for practical research and analytics use. Researchers had to create their own software for many years to utilize Bayesian networks. Needless to say, this made Bayesian networks inaccessible to the vast majority of scientists.

The launch of BayesiaLab 1.0 in 2002 was a major initiative by a newly formed French company to address this challenge. The development team, led by Dr. Lionel Jouffe and Dr. Paul Munteanu, designed BayesiaLab with research practitioners in mind—rather than fellow computer scientists. First and foremost, practitioner orientation is reflected in the graphical user interface of BayesiaLab, which allows researchers to work interactively with Bayesian networks in their native form using graphs, as opposed to working with computer code. At the time of writing, BayesiaLab is approaching its sixth major release and has developed into a software platform that provides a comprehensive “laboratory” environment for many research questions.

However, the point-and-click convenience of BayesiaLab does not relieve one of the duties of understanding the fundamentals of Bayesian networks for conducting sound research. With BayesiaLab making Bayesian networks accessible to a much broader audience than ever, demand for the corresponding training has grown tremendously. We recognized the need for a book that supports a self-guided exploration of this field. This book aims to provide a practice-oriented introduction to both Bayesian networks and BayesiaLab.

This book reflects the inherently visual nature of Bayesian networks. Hundreds of illustrations and screenshots provide a tutorial-style explanation of BayesiaLab’s core functions. Particularly important steps are repeatedly shown in the context of different examples. The key objective is to provide the reader with step-by-step instructions for transitioning from Bayesian network theory to fully functional implementations in BayesiaLab.

The fundamentals of the Bayesian network formalism are linked to numerous disciplines, including computer science, probability theory, information theory, logic, machine learning, and statistics. Also, in terms of applications, Bayesian networks can be utilized in virtually all disciplines. Hence, we meander across many fields of study with the examples presented in this book. Ultimately, we will show how all of them relate to the Bayesian network paradigm. At the same time, we present BayesiaLab as the technology platform, allowing the reader to move immediately from theory to practice. Our goal is to use practical examples to reveal the Bayesian network theory and simultaneously teach the BayesiaLab technology.

### Structure of the Book&#x20;

#### Part 1&#x20;

The three short chapters in Part 1 of the book aim to provide a basic familiarity with Bayesian networks and BayesiaLab, from which the reader should feel comfortable jumping into any of the subsequent chapters. Part 1 could serve as an executive summary for a cursory observer of this field.

* [Chapter 1](chapter-1-introduction.md) provides motivation for using Bayesian networks from the perspective of analytical modeling.
* [Chapter 2](chapter-2-bayesian-network-theory.md) is adapted from [Pearl and Russell (2000)](https://ftp.cs.ucla.edu/pub/stat\_ser/r277.pdf) and introduces the Bayesian network formalism and semantics.
* [Chapter 3](chapter-3-bayesialab.md) presents a brief overview of the BayesiaLab software platform and its core functions.

#### Part 2&#x20;

The chapters in Part 2 are mostly self-contained tutorials, which can be studied out of sequence. However, beyond [Chapter 8](chapter-8-probabilistic-structural-equation-models-for-key-driver-analysis/), we assume a certain degree of familiarity with BayesiaLab’s core functions.

* In [Chapter 4](chapter-4-knowledge-modeling-and-probabilistic-reasoning.md), we discuss how to encode causal knowledge in a Bayesian network for subsequent probabilistic reasoning. In fact, this is the field in which Bayesian networks gained prominence in the 1980s in the context of building expert systems.
* [Chapter 5](chapter-5-bayesian-networks-and-data/) introduces data and information theory as a foundation for subsequent chapters. BayesiaLab’s data handling techniques, such as the Data Import Wizard, including Discretization, are presented in this context. Furthermore, we describe a number of information-theoretic measures that will subsequently be required for machine learning and network analysis.
* [Chapter 6](chapter-6-supervised-learning/) introduces BayesiaLab’s Supervised Learning algorithms for predictive modeling in the context of a classification task in the field of cancer diagnostics.
* [Chapter 7](chapter-7-unsupervised-learning/) demonstrates BayesiaLab’s Unsupervised Learning algorithms for knowledge discovery from financial data.
* [Chapter 8](chapter-8-probabilistic-structural-equation-models-for-key-driver-analysis/) builds on these machine-learning methods and shows a prototypical research workflow for creating a Probabilistic Structural Equation Model for a market research application.
* [Chapter 9](chapter-9-missing-values-processing/) deals with missing values, which are typically not of principal research interest but adversely affect most studies. BayesiaLab leverages the conceptual advantages of machine learning and Bayesian networks to reliably impute missing values.
* [Chapter 10](https://www.bayesia.com/articles/bayesialab-knowledge-hub/10-causal-effect-estimation) closes the loop by returning to the topic of causality, which we first introduced in [Chapter 4](https://www.bayesia.com/articles/bayesialab-knowledge-hub/4-probabilistic-reasoning). We examine approaches for identifying and estimating causal effects from observational data. Simpson’s Paradox serves as an example for this study.
* [Chapter 11](chapter-11-causality-and-optimization/) showcases a practical implementation of the causal concepts introduced in the previous chapter. Marketing mix modeling and optimization serve as a prototypical example.
* [Chapter 12](chapter-12-attribution-contribution-and-counterfactuals.md) illustrates the complexity of the seemingly straightforward concepts of attribution and contribution. Bayesian networks can clarify their meaning and make their computation possible.

### Notation&#x20;

* BayesiaLab methods, functions, and components are capitalized and shown in bold type, e.g., **Data Import Wizard**. This helps distinguish between natural language expressions, such as "parameter estimation" in general and the **Parameter Estimation** function in BayesiaLab in particular. Furthermore, concepts that are central to BayesiaLab, such as **Entropy** and **Mutual Information**, are emphasized in the same fashion, even though they are not exclusive to the BayesiaLab software.
* Hyperlinks are blue, e.g., [BayesiaLab User Guide](../user-guide/).
* User interactions with menus, e.g., the Main Menu or any of the Context Menus, are highlighted with a gray background: `Main Menu > Learning > Supervised Learning > Markov Blanket`.   &#x20;
* Keyboard shortcuts are marked with a gray background, e.g., `Ctrl+S`.

