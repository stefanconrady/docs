# Aggregation of Multiple Variables

### Context

Similar to the workflow for the [Aggregation of a Single Variable](aggregation-of-single-variable.md), you can also perform an Aggregation of Multiple Variables.

We use the same auto buyer survey dataset to illustrate the process. In the auto industry, numerous schemes are used to group vehicle types and body styles into so-called segments. Each segment carries a descriptive name, e.g., Compact Car, Full-Size SUV, Minivan, Mid-Size Pickup, Mid-Size Crossover. In our dataset, we have four variables, which each represent such a segmentation scheme. While all these segmentation schemes roughly convey the same information, they differ in their granularity: for instance, variable Segmentation 3 has 23 states; Segmentation 4 has 33. Our objective is now to reduce each one of the segmentation schemes down to three states.

This time, instead of Price, we use the variable MPG - Combined as a target. It represents the survey respondents' estimates of their vehicles' combined fuel economy in miles per gallon (MPG). In other words, we want to create a new aggregation for each segmentation scheme based on fuel economy. Also, the variable MPG - Combined only has two intervals, with one threshold at 22.5. This number has been used in the past as a criterion for so-called "gas guzzlers." So, we are going to use the state <=22.5 as a proxy for poor fuel economy. As a result, we expect each of the existing segments to be "remapped" according to fuel economy.&#x20;

### Workflow

* In the Data panel, using Ctrl+Click or Shift+Click, select the variables Segmentation 1, Segmentation 2, Segmentation 3, and Segmentation 4.&#x20;
* This brings up the Multiple Aggregation panel.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/Aggregation/DataImportWizard-4-MultipleAggregationPanel.png" alt=""><figcaption></figcaption></figure>

* Set Target to MPG - Combined, and State to <=22.5.
* Set Final Number of States to 3.
* Click the Aggregate button to perform the aggregation.
* Note that there will be no immediate feedback regarding the results of the aggregation.
* Rather, we can only see the results of the aggregation in the Import Report in Step 5 of the Data Import Wizard.
* Click Finish to complete Step 4 of the Data Import Wizard.
* BayesiaLab opens a new Graph Window with all variables now presented as nodes.
* Simultaneously, a prompt comes up offering to display the Import Report.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/DataImportWizard-5/DataImportWizard-5-ImportReportPrompt.png" alt=""><figcaption></figcaption></figure>

* Click Yes, and the Import Report — featuring all variables, not just the aggregated variables — appears in a new window.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Open-Data-Source/DataImportWizard-5/DataImportWizard-5-ImportReportAggregationReport.png" alt=""><figcaption></figcaption></figure>

