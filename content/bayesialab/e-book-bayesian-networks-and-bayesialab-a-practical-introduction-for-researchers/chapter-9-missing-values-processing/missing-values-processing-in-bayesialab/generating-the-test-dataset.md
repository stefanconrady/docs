# Generating the Test Dataset

To begin this exercise, we use BayesiaLab to produce the test data that we will later use for evaluating the Missing Values Processing methods.

We can directly generate data according to the joint probability distribution encoded by the Reference Network: `Main Menu > Data > Generate Data`.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-18\_16-13-13.png)

Next, we must specify whether to generate this data internally or externally. For now, we generate the data internally, which means that we associate data points with all nodes. This includes missing values and Filtered Values according to the reference network.

For the Number of Examples (i.e., cases or records), we set 10,000.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-22\_18-17-02.png)

The Database icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184169/BayesiaLab\_Icons/database\_uxupjf.svg) signals that a dataset is now associated with the network. Additionally, we can see the number of cases in the database at the top of the Monitor Panel.

Now that this data exists inside BayesiaLab, we need to export it, so we can truly start “from scratch” with the test dataset. Also, regarding realism, we only want to make the observable variables available rather than all. We first select the nodes X1\_obs through X5\_obs and then select `Main Menu > Data > Save Data` from the main menu.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-22\_19-17-59.png)

Next, we confirm that we only want to save the Selected Nodes, i.e., the observable variables.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-22\_19-23-57.png)

Upon specifying a file name and saving the file, the export task is complete.

A quick look at the CSV file confirms that the newly generated data contain missing and Filtered Values, as indicated with question marks (?) and asterisks (\*), respectively.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690936817/Generating-Missing-Values-Test-Dataset_tzrucq.svg" alt="" width="563"><figcaption></figcaption></figure>

Now that we have produced a test dataset with all types of missingness, we forget our reference model to start “from scratch.” We approach this dataset as if this were the first time we see it, without any assumptions and without any background knowledge. This provides us with a suitable test case for BayesiaLab’s range of missing values processing methods.
