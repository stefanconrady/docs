# Pearson Correlation

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

* In BayesiaLab's approach to learning and analyzing Bayesian networks, statistical concepts play a secondary role compared to concepts from the field of Information Theory.
* Nevertheless, statistical measures, such as correlation, can provide certain insights that are unavailable from non-statistical measures.

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

The Pearson Correlation Coefficient $$r$$ between two nodes $$X$$ and $$Y$$ is defined as the covariance of the two corresponding variables divided by the product of their standard deviations:

$$
R = \frac{{{\mathop{\rm cov}} (X,Y)}}{{{\sigma _X}{\sigma _Y}}}
$$

Where the covariance is defined by:

$$
{\mathop{\rm cov}} (X,Y) = \sum\limits_{x,y} {p(x,y) \times ({V_x} - {v_X})} \times ({V_y} - {v_Y})
$$

And the standard deviation:&#x20;

$$
{\sigma _X} = \sqrt {{{\sum\limits_x {{p_x} \times ({V_x} - {v_X})} }^2}}
$$

* $${{V_x}}$$ is the value that is associated with the state $$x$$.
* $${{v_X}}$$ is the [Expected Value](https://bayesia.clickhelp.co/articles/bayesialab/faq-means-and-values-of-nodes) of the node $$X$$
* $${{p_x}}$$ is the marginal probability of state $$x$$ returned by the Bayesian network
* $${p(x,y)}$$ is the joint probability of states $$x$$ and $$y$$ returned by the Bayesian network

### Special Considerations <a href="#h2_519852009" id="h2_519852009"></a>

* For calculating the **Pearson Correlation** $$R$$, BayesiaLab must use the values of node states.
* In BayesiaLab, there are Discrete Nodes and Continuous Nodes with discretized numerical states. As a result, the value of a node's state may not always be apparent:
  * For Discrete Nodes that have states with integer or real values, BayesiaLab uses these numerical values directly.&#x20;
  * For Discrete Nodes that have states without values, e.g., {red, green, blue}, BayesiaLab uses the indices of the states as values, i.e., {red, green, blue} would have the values {0, 1, 2} for the purpose of calculating $$R$$. Note that the index of states starts at 0.
  * For Continuous Nodes, BayesiaLab uses these mean values of each interval.&#x20;
* Please see Mean, Value, and Standard Deviations for a detailed discussion.
