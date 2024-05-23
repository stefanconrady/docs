# Kullback-Leibler Divergence (Arc Force)

### Definition&#x20;

* In BayesiaLab, the **Kullback-Leibler Divergence** (or **KL Divergence**) is used to measure the strength of the relationship between two nodes that are directly connected by an arc.&#x20;
* We commonly refer to the **KL Divergence** also as **Arc Force**.
* Formally, ​the **Kullback-Leibler Divergence DKL** measures the difference between two distributions $$P$$ and $$Q$$.

$$D_{KL}(P({\cal X})\|Q({\cal X}))=\sum_{\cal X}P({\cal X})log_2\frac{P({\cal X})}{Q({\cal X})}$$

* For our purposes, we consider $$P$$ the Bayesian network that does include the arc for which we wish to compute the **Arc Force**, and $$Q$$ the Bayesian network that does not contain that arc but is otherwise identical.
* We interpret this difference **DKL** as the "force of the arc" or **Arc Force**.
* Note that Filtered Values are taken into account for computing the **Arc Force**.

{% hint style="info" %}
Throughout this website, we use **Kullback-Leibler Divergence**, **KL Divergence**, and **Arc Force** interchangeably.
{% endhint %}
