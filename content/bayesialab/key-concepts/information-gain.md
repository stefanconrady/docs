# Information Gain

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

The **Information Gain** regarding evidence $$E$$ is the difference between the:

* Log-Loss $$L{L_U}\left( E \right)$$, given an unconnected network $$U$$, i.e., a so-called straw model, in which all nodes are marginally independent;
* Log-Loss $$L{L_B}\left( E \right)$$ given a reference network $$B$$.

$$IG_B(E) = {\log _2}\left( {{{P({e_1},...,{e_n})} \over {\prod\limits_{i = 1}^n {P({e_i})} }}} \right) = L{L_U}(E) - L{L_B}(E)$$

{% hint style="info" %}
In earlier versions of BayesiaLab, **Information Gain** was named **Consistency**.
{% endhint %}

### Interpretation <a href="#h2__1631879480" id="h2__1631879480"></a>

The **Log-Loss** reflects the "cost" in bits of applying the network $$B$$ to evidence $$E$$, i.e., the number of bits that are needed to encode evidence $$E$$. The lower the probability of evidence $$E$$, the higher the **Log-Loss**.

As a result, a positive value of **Information Gain** would reflect a "cost-saving" for encoding evidence $$E$$ by virtue of having network $$B$$. In other words, encoding $$E$$ with network $$B$$ is less "costly" than encoding it with the straw model $$U$$. Therefore, evidence $$E$$ would be _consistent_ with network $$B$$.

Conversely, a negative **Information Gain** indicates a so-called _conflict_, **Log-Loss** of evidence $$E$$ is higher with the straw model $$U$$ compared to the reference network $$B$$. Note that conflicting evidence does not necessarily mean that the reference network is wrong. Rather, it probably indicates that such a set of evidence belongs to the tail of the distribution that is represented by the reference network $$B$$.

However, if evidence $$E$$ is drawn from the original data on which the reference network $$B$$ was originally learned, the probability of observing _conflicting_ evidence should be smaller than the probability of observing _consistent_ evidence.

So, for a network model to be useful, there should generally be more sets of evidence with a positive **Information Gain**, i.e., consistent observations, than sets of evidence with a negative **Information Gain**, i.e., conflicting observations.&#x20;

Therefore, the mean value of the **Information Gain** of a reference network $$B$$ compared to a straw model $$U$$ is a useful performance indicator of the reference network $$B$$.&#x20;

### Related BayesiaLab Functions <a href="#h2__2012451339" id="h2__2012451339"></a>

* Information Gain and Evidence Analysis
* Network Performance
