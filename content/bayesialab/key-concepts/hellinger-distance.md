# Hellinger Distance

The Hellinger distance measures the similarity or dissimilarity between two probability distributions. It is often used in statistics and information theory to compare how two probability distributions differ or overlap.

The Hellinger distance is often used in various applications, such as statistical hypothesis testing, image processing, machine learning, and ecology, where comparing and quantifying the similarity or difference between probability distributions is important.

For discrete probability distributions $$P$$ and $$Q$$ defined over the same probability space, the Hellinger distance is defined as:

$$
H(P,Q) = \frac{1}{{\sqrt 2 }}\sqrt {\sum\limits_{i = 1}^n {{{\left( {\sqrt {{p_i}}  - \sqrt {{q_i}} } \right)}^2}} }
$$

Where:

* $$H(P,Q)$$ is the Hellinger distance between distributions $$P$$ and $$Q$$.
* $$p_i$$ and $$q_i$$ are the probabilities associated with the $$i^{th}$$ event or outcome in the two distributions.

The Hellinger distance has several useful properties:

1. It is a metric: It satisfies the properties of a metric, which means it is non-negative, symmetric, and obeys the triangle inequality. In other words, it measures the distance between two distributions in a mathematically consistent way.
2. It is bounded: The Hellinger distance is bounded between 0 and $$\sqrt 2$$, where 0 indicates that the two distributions are identical, and $$\sqrt 2$$ indicates that they are entirely dissimilar.
3. Interpretability: The Hellinger distance has a meaningful interpretation in terms of probability distributions. It quantifies how much the square root of the probability density functions of the two distributions differ.
4. Square-root transformation: The square root transformation in the formula gives more weight to the differences in the tails of the distributions compared to other distance metrics like the [Kullback-Leibler (KL) divergence](kullback-leibler-divergence-arc-force.md) or the Bhattacharyya distance.

