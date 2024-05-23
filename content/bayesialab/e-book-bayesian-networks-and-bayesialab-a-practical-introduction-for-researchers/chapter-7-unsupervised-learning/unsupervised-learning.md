# Unsupervised Learning

### Unsupervised Learning <a href="#h2__1232181657" id="h2__1232181657"></a>

The computational complexity of BayesiaLab’s Unsupervised Learning algorithms exhibits quadratic growth as a function of the number of nodes. However, the Maximum Weight Spanning Tree (MWST) is constrained to learning a tree structure (one parent per node), which makes it much faster than the other algorithms. More specifically, the MWST algorithm includes only one procedure with quadratic complexity, namely the initialization procedure that computes the matrix of bivariate relationships.

Given the number of variables in this dataset, we decide to use the MWST. Performing the MWST algorithm with a file of this size should only take a few seconds. Moreover, using BayesiaLab’s layout algorithms, the tree structures produced by MWST can be easily transformed into easy-to-interpret layouts. Thus, MWST is a practical first step for knowledge discovery. Furthermore, this approach can be useful for verifying that there are no coding problems, e.g., with variables that are entirely unconnected. Given the quick insights that can be gleaned from it, we recommend using MWST at the beginning of most studies.

We return to Modeling Mode (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184233/BayesiaLab\_Icons/Modeling-Mode-Icon\_s6tz0u.svg) or ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1690829528/F4\_hiym4a.svg)) and select `Main Menu > Learning > Unsupervised Structural Learning > Maximum Spanning Tree`.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-07-19\_20-48-341.png)

In addition to its one-parent constraint, MWST is also unique in that it is the only learning algorithm in BayesiaLab that allows us to choose the scoring method for learning, i.e., [Minimum Description Length (MDL)](../../key-concepts/minimum-description-length-score/) or [Pearson’s Correlation](../../key-concepts/pearson-correlation.md). Unless we are certain about the linearity of the yet-to-be-learned relationships between variables, Minimum Description Length is the better choice and, hence, the default setting.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-17\_13-05-151.png)

At first glance, the resulting network does not appear simple and tree-like at all.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-17\_13-02-081.png)

This can be addressed with BayesiaLab’s built-in layout algorithms. `Selecting Main Menu > View > Automatic Layout` (Shortcut: ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1690848232/P\_a7qkow.svg)) quickly rearranges the network to reveal the tree structure. The resulting reformatted Bayesian network can now be readily interpreted.



<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690848432/SP500-MWST_q136kh.webp" alt=""><figcaption></figcaption></figure>

</div>

### Network Analysis <a href="#h2__994383314" id="h2__994383314"></a>

Let us suppose we are interested in Procter & Gamble (PG). First, we look for the corresponding node using the Search function (Ctrl+F). Note that we can search for the full company name if we check Include Comments. Furthermore, we can use a combination of wildcards in the search, e.g., “\*” as a placeholder for a character string of any length or “?” for a single character.

Selecting PG from the listing search results makes the corresponding node flash for a few seconds so it can be found among the hundreds of nodes on the screen.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/droppedImage-111.png)

Once located, we can zoom in to see PG and numerous adjacent nodes.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690848585/PG-Neighbors_dkn4cp.webp" alt=""><figcaption></figcaption></figure>

</div>

As it turns out, the “neighborhood” of Procter & Gamble contains many familiar company names, mostly from the consumer packaged goods industry. Perhaps these companies appear all too obvious, and one might wonder what insight we gained at this point. The chances are that even a casual observer of the industry would have mentioned Kimberly-Clark, Colgate-Palmolive, and Johnson & Johnson as businesses operating in the same field as Procter & Gamble. Therefore, one might argue similar stock price movements should be expected.

The key point here is that—without any prior knowledge of this domain—a computer algorithm automatically extracted a structure that is consistent with the understanding of anyone familiar with this domain.

Beyond interpreting the qualitative structure of this network, there is a wide range of functions for gaining insight into this high-dimensional problem domain. For instance, we may wish to know which node within this network is most important. In [Chapter 6](../chapter-6-supervised-learning/), we discussed the question in the context of a predictive model, which we learned with Supervised Learning. Here, on the other hand, we learned the network with an Unsupervised Learning algorithm, which means that there is no Target Node. As a result, we need to think about the importance of a node with regard to the entire network, as opposed to a specific Target Node.

We need to introduce a number of new concepts to equip us for the discussion about node importance within a network. We draw on concepts from information theory, which we first introduced in [Chapter 5](../chapter-5-bayesian-networks-and-data/) under Information-Theoretic Concepts.

#### Arc Force <a href="#h3_720999677" id="h3_720999677"></a>

BayesiaLab’s Arc Force is computed by using the [Kullback-Leibler Divergence](../../key-concepts/kullback-leibler-divergence-arc-force.md), denoted by $$D_{KL}$$, which compares two joint probability distributions, $$P$$ and $$Q$$, defined on the same set of variables $$X$$.

$$
{D_{KL}}\left( {P(X)\parallel Q(X)} \right) = \sum\limits_X {P(X){{\log }_2}{{P(X)} \over {Q(X)}}}
$$

where $$P$$ is the current network, and $$Q$$ is the exact same network as $$P$$, except that we removed the arc under study.

has noIt is important to note that [Mutual Information](../../key-concepts/mutual-information/) and [Arc Force](../../key-concepts/kullback-leibler-divergence-arc-force.md) are closely related (see [Comparing Mutual Information and Arc Force](../../key-concepts/mutual-information/comparing-mutual-information-and-arc-force.md)). If the child node in the pair of nodes under study has no other parents, Mutual Information and Arc Force are, in fact, equivalent. However, the Arc Force is more powerful as a measure as it considers the network’s [Joint Probability Distribution](../../key-concepts/joint-probability-and-joint-probability-distribution-jpd.md) rather than only focusing on the bivariate relationship.

The Arc Force can be displayed directly on the Bayesian network graph. Upon switching to the Validation Mode (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184241/BayesiaLab\_Icons/Validation-Mode-Icon\_ttnspc.svg) or ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1690829733/F5\_kgfoms.svg)), we select `Main Menu > Analysis > Visual > Arc Force`.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-26\_13-43-021.png)

Upon activating Arc Force, we can see that the arcs have different thicknesses. Also, an additional control panel becomes available in the menu.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-26\_13-46-431.png)

The slider in this control panel allows us to set the Arc Force threshold below which arcs and nodes will be grayed out in the Graph Panel. By default, it is set to 0, which means that the entire network is visible. Using the Previous and Next buttons, we can step through all threshold levels. For instance, by starting at the maximum and then going down one step, we highlight the arc with the strongest Arc Force in this network, which is between SPG (Simon Property Group) and VNO (Vornado Realty Trust).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-26\_13-55-231.png)

#### Node Force <a href="#h3__805824103" id="h3__805824103"></a>

The Node Force can be derived directly from the Arc Force. More specifically, there are three types of Node Force in BayesiaLab:

* The Incoming Node Force is the sum of the Arc Forces of all incoming arcs.
* The Outgoing Node Force is the sum of the Arc Forces of all outgoing arcs.
* The Total Node Force is the sum of the Arc Forces of all incoming and outgoing arcs.

The Node Force can be shown directly on the Bayesian network graph. Upon switching to the Validation Mode (F5), we select Analysis > Visual > Node Force.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-17\_13-28-291.png)

After starting Node Force, we have another additional control panel available in the menu.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-17\_14-34-001.png)

The slider in this control panel allows us to set the Node Force threshold below which nodes will be grayed out in the Graph Panel. By default, it is set to 0, meaning all nodes are visible. Conversely, by setting the threshold to the maximum, all nodes are grayed out. Using Previous and Next, we can step through the entire range of thresholds. This functionality is analogous to the control panel for Arc Force.&#x20;

For example, by starting at the maximum and then going down one step, we can find the node with the strongest Node Force in this network, which is BEN (Franklin Resources), a global investment management organization.&#x20;

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised\_Learning-web-resources/image/2015-08-17\_14-53-071.png)

#### Node Force Mapping <a href="#h3__1837547811" id="h3__1837547811"></a>

This analysis tool also features a “local” Mapping function, which is particularly useful when dealing with big networks, such as the one in this example with hundreds of nodes. We refer to this as a “local” Mapping function in the sense of only being available in the context of Node Force Analysis, as opposed to the “general” Mapping function, which is always available within the Validation Mode as a standalone analysis tool (`Main Menu > Analysis > Visual > Mapping`).

We launch the Mapping window by clicking the Mapping icon (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184122/BayesiaLab\_Icons/mapping\_rtobkg.svg)) on the control panel to the right of the slider. In this network view, the size of the nodes is directly proportional to the selected type of Node Force (Incoming, Outgoing, Total). The width of the links is proportional to the Arc Force. Changing the threshold values (with the slider, for example) automatically updates the view.

Choosing Static Font Size from the Contextual Menu and then, for instance, reducing the threshold by four more steps reveals the five strongest nodes while maintaining an overview of the entire network.

<div data-full-width="true">

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/7-Unsupervised_Learning-web-resources/image/2015-08-28_16-38-301.png" alt=""><figcaption></figcaption></figure>

</div>
