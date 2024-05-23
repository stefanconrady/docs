# Structural Coefficient

### Context <a href="#h2__807134280" id="h2__807134280"></a>

* BayesiaLab utilizes proprietary score-based learning algorithms.
* As opposed to the constraint-based algorithms that use independence tests for adding or removing arcs between nodes, BayesiaLab employs the [Minimum Description Length Score (MDL Score)](minimum-description-length-score/) to measure the quality of candidate networks with respect to the available data.

### Structural Coefficient <a href="#h2_1982399616" id="h2_1982399616"></a>

* In BayesiaLab, the computation of the [MDL Score](minimum-description-length-score/) also includes the so-called **Structural Coefficient** $$\alpha$$ as a weighting factor for the _structural_ component $$DL(B)$$.
* With that, the [MDL Score](minimum-description-length-score/) is calculated using the following formula:

$$MDL(B,D) = \alpha \times DL(B) + DL(D|B)$$

* As a result, the choice of value for the **Structural Coefficient** $$\alpha$$ affects the relative weighting of the two components $$DL(B)$$ and $$DL(D|B)$$.
* You can arbitrarily modify the **Structural Coefficient** $$\alpha$$ within the range of 0 to 150.&#x20;
* $$\alpha  = 1$$, the default value means the components $$DL(B)$$ and $$DL(D|B)$$ are weighted equally.
* $$\alpha  < 1$$ reduces the contribution of $$DL(B)$$ in the [MDL Score](minimum-description-length-score/) formula and, thus, allows for more "structural complexity."
* $$\alpha  > 1$$ increases the contribution of $$DL(B)$$ in the [MDL Score](minimum-description-length-score/) formula, i.e., it penalizes "structural complexity", forcing a simpler model. \

* There is another way to interpret the **Structural Coefficient** $$\alpha$$, which can help understand its role in learning a Bayesian network.
  * Weighting $$DL(B)$$ with a factor $$\alpha$$ is equivalent to changing the original number of observations N in a dataset to a new number of observations N′:

$$
N' = \frac{N}{\alpha }
$$

* An $$\alpha$$ value of 0 would be the same as having an infinite number of observations $$N'$$. As a result, the [MDL Score](minimum-description-length-score/) would only be based on the fit component of the score, i.e., $$DL(D|B)$$, and BayesiaLab's structural learning algorithms would produce a fully connected network.
* At the other extreme, an $$\alpha$$ value of 150 would massively favor the simplest possible network structures as the new equivalent number of observations $$N'$$ would only 1/150th of $$N$$.
* It is perhaps more intuitive to consider the new number of observations N′ as weighted counts of the actual observations $$N$$. For instance, $$\alpha  = 0.5$$ is equivalent to counting all observations twice.
* From a practical perspective, the **Structural Coefficient** $$\alpha$$ can be considered a kind of "significance" threshold for structural learning.
  * The higher you set the $$\alpha$$ value, the higher the threshold for discovering probabilistic relationships. Conversely, the lower you set the $$\alpha$$ value, the lower the discovery threshold and the weaker probabilistic relationship would still be found and represented by an arc.
  * Reducing α can be helpful if you have a small dataset from which you want to learn a model. Perhaps at the default value, $$\alpha  = 1$$, the learning algorithm would not find any arcs.
  * However, choosing too low a value might result in "overfitting", i.e., learning "insignificant" relationships, in other words, discovering patterns in what turns out to be mere noise.
  * BayesiaLab can help reduce the risk of overfitting with the Structural Coefficient Analysis feature.
