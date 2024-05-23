# Maximum Likelihood Estimation

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

* BayesiaLab estimates the parameters of a Bayesian network using **Maximum Likelihood Estimation**_._
* The probability of a state $${x_0}$$ of a node $${X}$$ corresponds to the frequency the state $${x_0}$$ is observed in the dataset.&#x20;

### Example <a href="#h2_1689083776" id="h2_1689083776"></a>

Let's consider this simple network:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Maximum-Likelihood-Estimation/Pa\_X.svg)\


#### Maximum Likelihood Estimation <a href="#h3__343344811" id="h3__343344811"></a>

The marginal probability distribution of $$Pa$$ is estimated as:

$$
\hat P(Pa = p{a_i}) = \frac{{N(Pa = p{a_i})}}{{\sum\nolimits_j {N(Pa = p{a_j})} }}
$$

where $$N\left(  \cdot  \right)$$ represents the number of occurrences of the specified configuration in the dataset.

The conditional probability distribution of X|Pa is estimated as

$$
\hat P(X = {x_i}|Pa = p{a_i}) = \frac{{N(X = {x_i},Pa = p{a_i})}}{{\sum\nolimits_j {N(X = {x_j},Pa = p{a_j})} }}
$$
