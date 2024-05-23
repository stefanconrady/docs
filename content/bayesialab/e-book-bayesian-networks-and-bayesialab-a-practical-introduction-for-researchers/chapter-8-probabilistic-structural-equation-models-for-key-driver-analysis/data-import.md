# Data Import

### Data Import&#x20;

We have already described all the steps of the [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/) in previous chapters. Therefore, we present most of the following screenshots without commentary and only highlight items specific to this example. To start the [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/), we open the file [Perfume.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1690851674/Perfume\_yciptt.csv).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-08-09\_18-44-461.png)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_20-39-151.png)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_20-43-061.png)

For this example, we need to override the default data type for the variable named Product as it is a nominal product identifier rather than a numerical value. We can change this variable’s data type by highlighting the Product column and clicking the Discrete radio button. This changes the color of the Product column to red. We also define Purchase Intent and Intensity as Discrete variables. Their number of states is suitable for our purposes.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_20-46-041.png)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_20-47-171.png)

The next step is the Discretization and Aggregation screen. Given the number of observations, it is appropriate to reduce the number of states of the ratings from the original 10 states (1–10) to a smaller number. All these variables measure satisfaction on the same scale, i.e., from 1 to 10. Following our earlier recommendations (see Discretization Intervals in Chapter 6), the best choice in this context is the Equal Distance discretization.

By clicking Select All Continuous, we highlight all to-be-discretized variables. Then, we choose the type of discretization to be applied, which is Equal Distance. Furthermore, given the number of observations, we choose 5 bins for the discretization.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_20-59-471.png)

Clicking Finish finalizes the import process. Upon completion, we are prompted whether we want to view the Import Report.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-06-27\_21-10-471.png)

As there is no uncertainty with regard to the outcome of the discretization, we decline and automatically obtain a fully unconnected network with 49 nodes.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/8-PSEM\_V2-web-resources/image/2015-08-09\_20-17-531.png)
