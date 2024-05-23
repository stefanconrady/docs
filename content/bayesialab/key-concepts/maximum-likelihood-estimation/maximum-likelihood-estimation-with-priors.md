# Maximum Likelihood Estimation with Priors

### Context <a href="#h3__1168384108" id="h3__1168384108"></a>

* BayesiaLab can also take into account Priors when estimating parameters using [Maximum Likelihood Estimation](./).
* Priors reflect any a priori knowledge of an analyst regarding the domain, in other words, expert knowledge. See also Prior Knowledge for Structural Learning.
* These priors are expressed with an analyst-specified, initial Bayesian network (structure and parameters) plus analyst-specified Prior Samples.
* Prior Samples represent the analyst's subjective degree of confidence in the Priors.

$$
\hat P(X = {x_i}|Pa = p{a_i}) = \frac{{N(X = {x_i},Pa = p{a_i}) + {M_0} \times {P_0}(X = {x_i},Pa = p{a_i})}}{{\sum\nolimits_j {\left( {N(X = {x_j},Pa = p{a_j}) + {M_0} \times {P_0}(X = {x_j},Pa = p{a_i})} \right)} }}
$$

where

* $${M_0}$$ is the degree of confidence in the Prior.
* $${P_0}$$ is the joint probability returned by the prior Bayesian network.
* BayesiaLab uses these two terms to generate _virtual_ samples that are subsequently combined with the _observed_ samples from the dataset.

### Virtual Database Generator <a href="#h4__1518761" id="h4__1518761"></a>

* With your current Bayesian network, you can generate Priors&#x20;
* Select  `Main Menu > Data > Prior Samples > Generate`.
* You can specify $${M_0}$$ by setting the number of Prior Samples.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/attachments/12320859/35652298.png)&#x20;

* BayesiaLab uses the current Bayesian network to compute $${P_0}$$.
* The existence of a new Virtual Database is indicated by an icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184063/BayesiaLab\_Icons/virtual-database\_o2nf2n.svg) in the lower right corner of the graph window, next to the "real dataset" icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184169/BayesiaLab\_Icons/database\_uxupjf.svg).\

* Right-clicking on the Virtual Database icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184063/BayesiaLab\_Icons/virtual-database\_o2nf2n.svg) displays the structure of the prior knowledge that was used for generating the Virtual Samples.
* These Virtual Samples will be combined with the observed "real" samples during the learning process.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/attachments/12320859/12582917.png)

#### Number of Uniform Prior Samples <a href="#h3__694922507" id="h3__694922507"></a>

* **Edit Number of Uniform Prior Samples** allows you to define prior knowledge in such a way that all the variables are marginally independent (fully unconnected network), and the marginal probability distributions of all nodes are uniform.
*   For instance, if the number of Prior Samples is set to 1, one observation ("occurrence") would be "spread across" all states of each node, essentially assigning a "fraction of an observation" to each node's states.

    * To apply Smoothed Probability Estimation, select `Main Menu > Edit > Edit Smoothed Probability Estimation`
    * Specify the number of Prior Samples.

    ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/attachments/12320859/35652299.png)
