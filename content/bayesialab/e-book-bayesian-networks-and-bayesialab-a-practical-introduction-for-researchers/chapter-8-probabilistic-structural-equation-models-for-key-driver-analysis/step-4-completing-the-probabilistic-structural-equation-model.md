# Step 4: Completing the Probabilistic Structural Equation Model

Based on the “final” network, we can proceed to the next step in our network-building process. We now introduce Purchase Intent, which has been excluded up to this point. Clicking this node while holding `X` renders it “un-excluded.” This makes Purchase Intent available for learning. Additionally, we designate Purchase Intent as Target Node by double-clicking the node while holding `T`.

Looking for an SEM-type network structure stipulates that Manifest variables be connected exclusively to the Factors and that all the connections with Purchase Intent must go through the factors. We have already imposed this constraint by setting the option Forbid New Relations with Manifest Variables in the Multiple Clustering dialog box. This created so-called Forbidden Arcs, which prevent learning algorithms from creating new arcs between the specified nodes. BayesiaLab indicates the presence of Forbidden Arcs with an ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184142/BayesiaLab\_Icons/forbidden-arcs\_aj8acf.svg) icon in the lower right-hand corner of the Graph Panel window. Clicking on the icon brings up the Forbidden Arc Editor, which allows us to review the currently set constraints. We see that the nodes belonging to the Class Manifest must not have any links to any other nodes, i.e., both directions are “forbidden.”

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-07-08\_16-53-411.png)

Upon confirming these constraints, we start Unsupervised Learning to generate a network that includes the Factors and the Target Node. In this particular situation, we need to utilize Taboo Learning. It is the only algorithm in BayesiaLab that can learn a new structure on top of an existing network structure and simultaneously guarantee to keep Fixed Arcs unchanged (EQ can also be used for structural learning on top of an existing network, but as it searches in the space of Essential Graphs, there is no guarantee that the Fixed Arcs remain unchanged). This is important as the arcs linking the Factors and their Manifest variables are such Fixed Arcs. To distinguish them visually, Fixed Arcs appear as dotted lines in the network instead of the solid lines of “regular” arcs.

We start Taboo Learning from the main menu by selecting `Main Menu > Learning > Unsupervised Structural Learning > Taboo` and check the option Keep Network Structure in the Taboo Learning dialog box.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-09-06\_17-15-101.png)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-08-10\_20-26-141.png)

Upon completing the learning process, we obtain the network shown below.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-09-06\_17-16-291.png)

As in [Step 1](step-1-unsupervised-learning.md), we also try to improve the quality of this network by using the Data Perturbation algorithm.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-09-06\_17-21-101.png)

As it turns out, this algorithm allowed us to escape from a local optimum and returned a final network with a lower [MDL Score](../../key-concepts/minimum-description-length-score/). Using Automatic Layout `P` and turning on Node Comments, we can quickly transform this network into a more interpretable format.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/111.png)

Now we see how the manifest variables are “laddering up” to the Factors and how the Factors are related to each other. Most importantly, we can observe where the Purchase Intent node was attached to the network during the learning process. The structure conveys that Purchase Intent is only connected to \[Factor\_2], which is labeled with the Node Comment “Pleasure\_(4).”
