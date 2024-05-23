# Log-Loss

### Definition <a href="#h3__1695316360" id="h3__1695316360"></a>

The Log-Loss $$LL(E)$$ reflects the number of bits required to encode an n-dimensional piece of evidence (or observation) $$E$$ given the current Bayesian network $$B$$. As a shorthand for "the number of bits required to encode," we use the term "cost" in the sense that "more bits required" means computationally "more expensive."

$$L{L_B}(E) = - {\log _2}\left( {{P_B}(E)} \right),$$

where $${{P_B}(E)}$$ is the joint probability of the evidence $$E$$ computed by the network $$B$$:

$$P_B(E) = P_B({e_1},...,{e_n})$$

In other words, the lower the probability of $$E$$ given the network $$B$$, the higher the Log-Loss $$LL(E)$$.&#x20;

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/User-Guide/Menus/Analysis/Report/Evidence/Information-Gain/LL(E)vsP(E).svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note that $$E$$ refers to a single piece of n-dimensional evidence, not an entire dataset.
{% endhint %}
