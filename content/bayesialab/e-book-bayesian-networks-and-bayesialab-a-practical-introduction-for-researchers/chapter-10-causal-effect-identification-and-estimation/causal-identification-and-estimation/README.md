# Causal Identification and Estimation

We will now explore formal methodologies that can help us derive causal effects from observational data. These methodologies will ultimately allow us to answer the question raised by Simpson’s Paradox. The process of determining the size of a causal effect from observational data can be divided into two steps, namely identification, and estimation.

### Identification

Identification analysis is about determining whether or not a causal effect can be established from the observed data. This requires a formal causal model or at least partial knowledge of how the data was generated. In this chapter, all causal assumptions for identification are expressed explicitly in the form of a Directed Acyclic Graph (DAG) (Pearl 1995, 2009). They represent our complete causal understanding of the DGP for the system we are studying.

Where do we get such causal assumptions? We would like to say that advanced algorithms can generate causal assumptions from data. That is not the case, unfortunately. Causal assumptions do still require human expert knowledge or, more generally, theory. In practice, this means that we need to build (or draw) a causal graph of our domain. Then, we can examine this graph against formal criteria, which determine whether the effect is identifiable or not.

It is important to realize that the absence of causal assumptions cannot be compensated for by clever statistical techniques or by providing more data. So, recognizing that a causal effect is not identifiable brings the effect analysis to an abrupt halt.

### Estimation

But if the causal effect is identifiable, we can proceed to estimate the effect size. The same criteria that determine identifiability do also tell us how to perform the effect estimation. With that, we can utilize the available observational data and estimate the causal effect. Depending on the complexity of the domain, the effect estimation can bring a new set of challenges. However, in the context of Simpson’s Paradox, the effect estimation will be very straightforward.

### Identification and Estimation Methods <a href="#h2_934734805" id="h2_934734805"></a>

{% content-ref url="causal-dags.md" %}
[causal-dags.md](causal-dags.md)
{% endcontent-ref %}

{% content-ref url="graphical-identification-criteria.md" %}
[graphical-identification-criteria.md](graphical-identification-criteria.md)
{% endcontent-ref %}

{% content-ref url="effect-estimation/" %}
[effect-estimation](effect-estimation/)
{% endcontent-ref %}
