# Associate Data Source (Data Association Wizard)

### Context

[Open Data Source (Data Import Wizard)](open-data-source-data-import-wizard/) brings data into BayesiaLab to create a new Bayesian network, while Associate Data Source (Data Association Wizard) adds new data to a pre-existing network.&#x20;

BayesiaLab can load data from flat text files (e.g., CSV, TXT) or connected databases.

### Usage <a href="#h2__1033115260_1381251416" id="h2__1033115260_1381251416"></a>

* There are a total of six steps in the Data Association Wizard, which are mostly identical to the steps in the [Data Import Wizard](../../../e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-5-bayesian-networks-and-data/data-import-and-discretization.md).
* To launch the **Data Association Wizard** for a data table in a&#x20;
  * text file, select `Main Menu > Data > Open Data Source > Text File`.
  * database, select `Main Menu > Data > Open Data Source > Database`.

### Workflow

#### Step 1 — Data Structure Definition

* See Step 1 of the Data Import Wizard

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_14_19_ejdfji.png" alt=""><figcaption></figcaption></figure>

#### Step 2 — Definition of Variable Types&#x20;

* See Step 2 of the Data Import Wizard.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_19_13_k2g1x4.png" alt=""><figcaption></figcaption></figure>

* Additionally, clicking the **Unmatched Columns** button displays all the columns in the database that are not in the network.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_22_01_xp3ce8.png" alt=""><figcaption></figcaption></figure>

* The Unmatched Columns window allows you to select whether to use or not use the unmatched columns from the new dataset.

#### Step 3 — Data Selection, Filtering, and Missing Value Processing

* See [Step 3 of the Data Import Wizard](associate-data-source-data-association-wizard.md#step-3-missing-value-processing-and-data-filtering)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_29_23_mvwl7r.png" alt=""><figcaption></figcaption></figure>

#### Step 4 — Node and Node State Association

* This step links the variables in the dataset to the nodes of the network.&#x20;
* As such, this step depends on the three previous steps and the selection of variable types.
* Here you can define how the variables in the to-be-associated dataset will be mapped to the nodes already in the network.
* The following assignments are possible:
  * Discrete variable in the dataset → Discrete node in the network
  * Discrete variable in the dataset → Continuous node in the network
  * Continuous variable in the dataset → Continuous node in the network
* If variables in the dataset have the same name and type as existing nodes in the network, BayesiaLab will automatically propose an association.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_40_26_mv1clt.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331073/Associate-Data-Source_Time_0_00_47_12_ynbiam.png" alt=""><figcaption></figcaption></figure>

#### Step 5 — Discretization and Aggregation

* See [Step 4 of the Data Import Wizard](associate-data-source-data-association-wizard.md#step-4-node-and-state-associations)

#### Step 6 — Data Association Report

* See [Step 5 of the Data Import Wizard](open-data-source-data-import-wizard/step-5-import-report.md)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690331074/Associate-Data-Source_Time_0_01_09_06_tnodhs.png" alt=""><figcaption></figcaption></figure>

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690330596/Associate-Data-Source_usvkej.mp4" %}

\












































The **zone** **1** contains the list of the variables contained in the database and not already associated to a node of the network or added as a new node of the network. As you can see, the variable Geographic Zone contained in the database is discrete and has no corresponding node in the network. If you want to add it as a new node, select it and click on the button ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556356.png) , otherwise, if you don't want to add it, do nothing.&#x20;

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556355.png" alt=""><figcaption></figcaption></figure>

You can process in the same way for the continuous node N. You can also select and add several nodes at the same time.

The **zone** **2** contains the list of the nodes contained in the network and not already associated to a column of the database. If you want to link a variable from the database to a node of the network, simply select each one and press the button ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556356.png) . All remaining nodes in this list will not be linked to a column of the database and will be considered as hidden node in the network.

The **zone 3** contains the buttons used to add or remove associations.

The **zone** **4** contains the list of associations. It can contain also added variables from the database that will be treated as new nodes in the network. A double-click on an association display, if necessary, a dialog used to edit a discrete or a continuous association. As you can see, some associations show a warning icon. This icon indicates that some unusual behaviors are present in those associations.

The **zone** **5** contains a list containing the details of each warning of associations located in zone 4. If you select a warning in the list, the corresponding association will be selected in the zone 4. When the mouse hovers on the list, a tooltip shows the content of the warning. A double-click on it opens the convenient association editor in order to verify or modify the association. If you want to remove an asso- ciation or an added node, select it in the list and press the button ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556357.png) .

The **zone** **6** contains three buttons. The first and second buttons allow extending automatically the minimum and maximum of each continuous node that does not fit the database's limits. The third button allows filtering automatically each row that does not fit the network's limits.

#### Discrete Column Association

When you want to add or edit an association between a **discrete** **column** of the database and a **discrete** or **continuous node**, a dialog box appears:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556358.png)\
\
The **zone** **1** contains the list of the states from the database that are not already linked to a state of the node or directly added as a new state. To perform an association, select a state in the zone1 and a state in the zone 2 and press . If you want to add a state without linking it to a state of the node, simply select it and press the button .

The **zone** **2** contains the list of the states from the node of the network. This list will never be modified. Even if an association is done, the corresponding state of this list will not be removed and can be reused for another association. It allows linking several states from the database to the same state of the node from the network. To perform an association, select a state in the zone1 and a state in the zone 2 and press ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556356.png) . The state from the zone 1 will be removed and the association will be added in the zone 4.

The **zone 3** contains the buttons to add or remove states' associations.

The **zone** **4** contains all the associated and added states. An association can be removed by selecting it in the list and pressing the button ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556357.png) .

After association, the dialog looks like:\
\
![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556360.png)\
\
If there are still some states not linked in zone 1, **these** **states** **will** **be** **removed** **from** **the** **database**.

By default, the database's states which are the same as the network's ones, as the aggregates or as the states' long names will be automatically linked.

If filtered values exist in the database but are not declared in the network, it is possible to merge them with the specific state \*, if it exists. In this case, this state will be automatically defined as filtered for each concerned node.

#### Continuous Column Association

When you want to add or edit an association between a **continuous** **column** of the database and a **continuous node**, a dialog box appears:

\
![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392493/2556361.png)

This dialog is displayed only if the limits of the variable from the database are outside the limits of the node from the network.

By default, the limits of the node of the network are used and **all** **the** **values** **outside** **these** **limits** **will be removed from the database**. If you want to keep them, use the corresponding options.

If filtered values exist in the database but are not declared in the network, it is possible to merge them with the specific state \*, if it exists. In this case, this state will be automatically defined as filtered for each concerned node.

#### Step 5: Discretization of the Continuous Variables and State Aggregation of the Discrete Variables

This step occurs only when some columns of the database are not linked with nodes of the network but are distributed. These columns will create new nodes in the network and must be discretized if they are continuous and their states can be aggregated if they are discrete.

Same as **Step 4** in **Data Importation** **Wizard**.

#### Step 6: Associate Report

After successful data import, it is possible to display the HTML associate report.\
\
![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392496/2556449.png)\
\
This report may contain three tables:&#x20;

1. The modified nodes table:
   * For the discrete nodes, will be indicated, if necessary, the correspondence between the states in the database and in the network.
   * For the continuous nodes, will be indicated, if necessary, the initial minimum of the data and the retained final minimum and also the initial maximum and the retained final maximum.\
     &#x20;
2. The hidden nodes table: indicates the node that are in the network and that don't have any associated data.\
   &#x20;
3. The added nodes table: indicate the list of variables added to the network from the database. This table is the same as in the **import report**&#x20;

\
