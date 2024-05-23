# Aggregation of Single Variable

Individual variables can be aggregated manually or automatically in [Step 4 of the Data Import Wizard](../).

To illustrate all related workflows, we use an American auto buyer satisfaction survey containing 42,397 responses. Each record contains attributes of the purchased vehicle, such as make (or brand), model, body style, vehicle segment, number of cylinders, transmission, price paid, self-reported fuel economy, plus hundreds of other variables.

### Manual Aggregation

First, we want to manually aggregate all 37 automobile brands that appear in the survey into just two states, i.e., Premium Brands and Non-Premium Brands.&#x20;

This manual aggregation will be based exclusively on our subjective perception of the auto industry as of 2009, which is when this particular survey was conducted. &#x20;

* Click on the Brand variable in the Data panel.
* From the States list on the left, select the values you wish to aggregate using Shift+Click or Ctrl+Click.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualStatesPanel.png" alt=""><figcaption></figcaption></figure>

* Then, click the Aggregate button.
* The newly-formed, aggregated state appears in the Aggregates list on the right.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualAggregatesPanel.png" alt=""><figcaption></figcaption></figure>

* By default, the original values are concatenated using the "+" symbol as a delimiter. An underscore "\_" is added as a prefix.
* As necessary, you can select more values from the States list and create additional aggregated states.
* In the list of Aggregates, you can now replace the automatically-generated state names with more meaningful ones.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualAggregatesPanelPremium.png" alt=""><figcaption></figcaption></figure>

* You can now proceed to any other variable or click Finish to conclude the Data Import Wizard.

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690312349/DataImportWizard-4-AggregationSingleCorrelation_kno9v6.mp4" %}

### Correlation-Aided Manual Aggregation

In addition to the [Manual Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation-aggregation/a/h3\_914436621) described above, BayesiaLab can support you in making the aggregation decisions. For this purpose, BayesiaLab can show how the original values of the to-be-aggregated variable correlate with those of other variables.

Continuing with the previous example, we now perform an aggregation of the same variable, Brand. Now, however, we use each brand's correlation with Price as a guide instead of our judgment.

For the purpose of this demonstration, we have already discretized the Price variable manually into three (arbitrary) intervals using two thresholds, i.e., $25,000 and $45,000.

We now want to use the correlation of each brand with the top interval, i.e., $45,000+, as a measure of its "premium appeal" so that we can reduce the 37 brands into three states, Mainstream, Premium, and Luxury.&#x20;

For reference, 8.65% of all survey responses reported a vehicle purchase price of $45,000 or higher.&#x20;

### Workflow Instructions

* Click on the Brand variable in the Data panel.
* Click the Show Correlations box.
* Select Target and State.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualAggregatesShowCorreltaions.png" alt=""><figcaption></figcaption></figure>

* Review the values shown in the Correlations column. By hovering with your cursor over the Correlation bars in each row, a Tooltip displays the percentage difference of the corresponding row versus the marginal value.&#x20;
* The colored bars show how each value compares to the marginal probability of the selected state of the target. A green-colored bar indicates a probability higher than the marginal probability, and a red bar suggests a lower probability.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualCorrelationsPanel.png" alt=""><figcaption></figcaption></figure>

* Select the states to aggregate using Ctrl+Click.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualCorrelationsPanel2.png" alt=""><figcaption></figcaption></figure>

* Once you have selected the values, click the Aggregate button.
* The newly aggregated values now appear as a single item in the Aggregates list.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualAggregatesPanelLuxury.png" alt=""><figcaption></figcaption></figure>

* Review the newly aggregated states and, if necessary, assign new names to replace the ones that were generated automatically.
* To reverse the aggregation select the aggregated items in the Aggregates list and click Delete.

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690312349/DataImportWizard-4-AggregationSingleCorrelation_kno9v6.mp4" %}

### Correlation-Aided Automatic Aggregation

The Correlation-Aided Automatic Aggregation is very similar to the [Correlation-Aided Manual Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation-aggregation-single/a/Correlation-Aided%20Manual%20Aggregation).

The principal difference is that you don't select your to-be-aggregated values manually but rather specify thresholds that determine the aggregation.

So, the initial steps are analogous to the [Correlation-Aided Manual Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation-aggregation-single/a/Correlation-Aided%20Manual%20Aggregation).&#x20;

* Click on a Discrete variable in the Data panel.
* Click the Show Correlations box.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualAggregatesShowCorreltaions.png" alt=""><figcaption></figcaption></figure>

* Select Target and State.
* Review the values shown in the Correlations column. By hovering with your cursor over the Correlation bars in each row, a Tooltip displays the percentage difference of the corresponding row versus the marginal value.&#x20;
* The colored bars show how each value compares to the marginal probability of the selected state of the target. A green-colored bar indicates a probability higher than the marginal probability, and a red bar suggests a lower probability.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleManualCorrelationsPanel2.png" alt=""><figcaption></figcaption></figure>

* Now, instead of manually selecting the values you want to aggregate, click the Automatic Aggregation button.
* The Automatic Aggregation window opens up.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleAutomaticAggregation.png" alt=""><figcaption></figcaption></figure>

* The colored bar at the top visualizes the percentage differences versus the marginal probability of the selected state of the target.
* In our example, there is one brand, Mercury, which had no observations in the $45,000+ interval. As a result, it marks the bottom end of the spectrum, i.e., it is 8.65 percentage points below the marginal probability.
* On the other end of the spectrum, Porsche is 83.97 percentage points above the marginal probability.
* A default threshold is shown for 0, which is marked by the pink-to-red color change in the bar.
* You can manually add thresholds by right-clicking on the bar.
* As soon as you add a threshold, a corresponding entry appears in the list below.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleAutomaticAggregationAdd.png" alt=""><figcaption></figcaption></figure>

* Right-clicking again on an existing threshold removes that threshold.
* You can move an existing threshold by clicking on it and then dragging it to the desired value.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleAutomaticAggregationMove.png" alt=""><figcaption></figcaption></figure>

* Also, in the table below the colored bar, you can type in a threshold value.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleAutomaticAggregationType.png" alt=""><figcaption></figcaption></figure>

* By clicking OK, you confirm the specified thresholds, and all values in the States list will be aggregated accordingly.
* Alternatively, you can click on Generate Aggregates and specify the desired number of intervals.
* You obtain a set of aggregation thresholds, which you can further modify or accept by clicking OK.
* Now you have a new set of states in the list of Aggregates.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-SingleAutomaticAggregationResults.png" alt=""><figcaption></figcaption></figure>

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690312940/DataImportWizard-4-AggregationSingleAutomatic2_dsxbt9.mp4" %}
