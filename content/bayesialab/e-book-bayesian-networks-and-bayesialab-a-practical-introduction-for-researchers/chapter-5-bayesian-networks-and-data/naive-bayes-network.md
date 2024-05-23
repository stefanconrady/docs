# Naive Bayes Network

Rather than computing the relationships individually for each pair of nodes, we ask BayesiaLab to estimate a Naive Bayes network. A Naive Bayes structure is a network with only one parent, the Target Node, i.e., the only arcs in the graph are those directly connecting the [Target Node](https://bayesia.clickhelp.co/articles/bayesialab/graph-windows-graph-panel-target-node-target-state) to a set of nodes. By designating SalePrice as the Target Node, we can automatically compute its Mutual Information with all other available nodes.

For the node he SalePrice, we select `Node Context Menu > Set as Target Node`. Alternatively, we can double-click the node while pressing `T`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/NodeContextMenuSetAsTargetNode.png" alt=""><figcaption></figcaption></figure>

The special status of the Target Node is highlighted by the bullseye symbol ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184213/BayesiaLab\_Icons/N6-Target\_qwed3w.svg). We can now proceed to learn the Naive Bayes network: `Select Main Menu > Learning Supervised Learning > Naive Bayes`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/LearningNaiveBayes.png" alt=""><figcaption></figcaption></figure>

Strictly speaking, we are not learning a network in the true sense of machine learning. Rather, we are specifying a naive structure, i.e., arcs from the Target Node to all other nodes, and then estimating the parameters.

Due to its simplicity, the Naive Bayes network is presumably the most commonly used Bayesian network. As a result, we find it implemented in many software packages. For instance, the so-called Bayesian anti-spam systems are based on this model.

However, it is important to note that the Naive Bayes network is merely the first step towards embracing the Bayesian network paradigm.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/AmesNaiveBayes.png" alt=""><figcaption></figcaption></figure>

Now we have the network that allows computing the [Mutual Information](../../key-concepts/mutual-information/) between all nodes.

We switch to [Validation Mode](../../user-guide/main-menu/view/validation-mode.md) ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184062/BayesiaLab\_Icons/validation\_ivi5eq.svg) and select `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/AnalysisVisualOverallArcMutualInformation.png" alt=""><figcaption></figcaption></figure>

The different levels of [Mutual Information](../../key-concepts/mutual-information/) are now reflected in the thickness of the arcs.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/ArcsMutualInformation.png" alt=""><figcaption></figcaption></figure>

However, given the grid layout of the nodes and the overlapping arcs, it is difficult to establish a rank order of the nodes in terms of [Mutual Information](../../key-concepts/mutual-information/). To address this, we adjust the layout and select `Main Menu > View > Layout > Radial Layout`.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/MainMenuViewLayoutRadialLayout.png)

This generates a circular arrangement of all nodes with the Target Node, SalePrice, in the center. Clicking the Stretch icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184078/BayesiaLab\_Icons/stretch\_eidjif.svg) repeatedly, we expand the network to make it fit into the available screen space widthwise.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/RadialLayout.png" alt=""><figcaption></figcaption></figure>

Also, having run the Radial Layout while the Arc Mutual Information function was still active, the arcs and nodes are ordered clockwise from strongest to weakest [Mutual Information](../../key-concepts/mutual-information/).

To improve the interpretability further, we select `Main Menu > View > Hide Information`. Alternatively, we click the Hide Information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184151/BayesiaLab\_Icons/barred-information\_icllgu.svg) in the Toolbar. This removes the information icons ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) from the arcs. Their presence indicates that further information would be available to display, e.g., the numerical values of the [Mutual Information](../../key-concepts/mutual-information/) of each arc.

The following standalone graphic highlights the order of the arcs and nodes in this Naive Bayes network:

&#x20;&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689983335/ArcMutualInformationRadialLayout_nh5iym.svg" alt=""><figcaption></figcaption></figure>

This illustration shows that Neighborhood provides the highest amount of [Mutual Information](../../key-concepts/mutual-information/) and, at the opposite end of the range, RoofMtl (Roof Material) the least.

As an alternative to this visualization, we can run a report `Main Menu Analysis > Report > Relationship`:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/MainMenuAnalysisReportRelationship.png)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/5-Bayesian-Networks-and-Data/RelationshipAnalysisReport.png" alt=""><figcaption></figcaption></figure>

Wouldn’t this report look the same if computed based on correlation? In fact, the rightmost column in this Relationship Analysis Report shows Pearson’s Correlation for reference. As we can see, the order would be different if we chose Pearson’s Correlation as the main metric.

So, what have we gained anything over correlation? One of the key advantages of Mutual Information is that it can be computed—and interpreted—between numerical and categorical variables without any variable transformation. For instance, we can easily compute the Mutual Information, such as between the Neighborhood and SalePrice. The question regarding the most important predictive variable can now be answered. It is Neighborhood.

Now that we have established the central role of Entropy and Mutual Information, we can apply these concepts in the next chapters for machine learning and network analysis.
