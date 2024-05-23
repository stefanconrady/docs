# Chapter 10: Causal Effect Identification and Estimation

### Introduction <a href="#h2__1296687178" id="h2__1296687178"></a>

> Δημόκριτος έλεγε βούλεσθαι μάλλον μίαν ευρείν αιτιολογίαν ή την Περσών βασιλείαν εαυτού γενέσθαι.” (“Democritus used to say that ‘he prefers to discover a causality rather than become a king of Persia’.”) — Democritus, according to a late testimony of Dionysius, Bishop of Alexandria, by Eusebius of Caesarea in Præparatio Evangelica (Εὑαγγελικὴ προπαρασκευή)

Bayesian Belief networks and modern causality analysis are intimately tied to the seminal works of Judea Pearl. It is presumably fair to say that one of the “unique selling points” of Bayesian networks is their capability to perform causal inference. However, we do want to go beyond merely demonstrating the mechanics of causal inference. Rather, we want to establish under what conditions causal inference can be performed. More specifically, we want to see the assumptions required to perform causal inference with non-experimental data.

To approach this topic, we need to break with the pattern established in the earlier chapters of this book. Instead of starting with a case study, we start off at a higher level of abstraction. First, we discuss in theoretical terms what is required for performing causal identification, estimation, and inference. Once these fundamentals are established, we can proceed to discuss the methods, along with their limitations, including Directed Acyclic Graphs and Bayesian networks. These techniques can help us distinguish causation from association when working with non-experimental data.

This chapter was prepared in collaboration with Felix Elwert on the basis of his course, Causal Inference with Graphical Models.

### Motivation: Causality for Policy Assessment and Impact Analysis <a href="#h2__835072907" id="h2__835072907"></a>

In this chapter, we discuss causality mostly on the basis of a “toy problem,” i.e., a simplified and exaggerated version of a real-world challenge. As such, the issues we raise about causality may appear somewhat contrived. Additionally, the constant practical use of causal inference in our daily lives may make our discussion seem somewhat artificial.

To highlight the importance of causal inference on a large scale, we want to consider how and under what conditions big decisions are typically made. Major government or business initiatives generally call for extensive studies to anticipate the consequences of actions not yet taken. Such studies are often referred to as “policy analysis” or “impact assessment”:

* “Impact assessment, simply defined, is the process of identifying the future consequences of a current or proposed action.” ([IAIA, 2009](https://www.iaia.org/about.php))
* “Policy assessment seeks to inform decision-makers by predicting and evaluating the potential impacts of policy options.” ([Adelle and Weiland, 2012](https://www.tandfonline.com/doi/full/10.1080/14615517.2012.663256))

What can be the source of such predictive powers? Policy analysis must discover a causal mechanism that links a proposed action/policy to a potential consequence/impact. Unfortunately, experiments are typically out of the question in this context. Rather, impact assessments—from non-experimental observations alone—must determine the existence and the size of a causal effect.

Given the sheer number of impact analyses performed and their tremendous weight in decision-making, one would like to believe that there has been a long-established scientific foundation with regard to (non-experimental) causal effect identification, estimation, and inference. Quite naturally, as decision-makers quote statistics in support of policies, the field of statistics comes to mind as the discipline that studies such causal questions.

However, casual observers may be surprised to hear that causality has been anathema to statisticians for the longest time.&#x20;

> "Considerations of causality should be treated as they always have been treated in statistics, preferably not at all..." (Speed, 1990).

The repercussions of this chasm between statistics and causality can still be felt today. Judea Pearl highlights this unfortunate state of affairs in the preface of his book Causality:&#x20;

> "… I see no greater impediment to scientific progress than the prevailing practice of focusing all our mathematical resources on probabilistic and statistical inferences while leaving causal considerations to the mercy of intuition and good judgment." (Pearl, 1999)

Rubin (1974) and Holland (1986), who introduced the counterfactual (potential outcomes) approach to causal inference, can be credited with overcoming statisticians’ traditional reluctance to engage causality. However, it will take many years for this fairly recent academic consensus to fully reach the world of practitioners, which is one of our key drivers for promoting Bayesian networks.

### Key Concepts, Methods, and Practical Implementation <a href="#h2_993801743" id="h2_993801743"></a>

Please read the following subchapters in sequence to receive a complete explanation.&#x20;

{% content-ref url="sources-of-causal-information.md" %}
[sources-of-causal-information.md](sources-of-causal-information.md)
{% endcontent-ref %}

{% content-ref url="example-simpsons-paradox.md" %}
[example-simpsons-paradox.md](example-simpsons-paradox.md)
{% endcontent-ref %}

{% content-ref url="causal-identification-and-estimation/" %}
[causal-identification-and-estimation](causal-identification-and-estimation/)
{% endcontent-ref %}

{% content-ref url="example-augmented-simpsons-paradox.md" %}
[example-augmented-simpsons-paradox.md](example-augmented-simpsons-paradox.md)
{% endcontent-ref %}
