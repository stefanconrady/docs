# Manual Discretization

### Context <a href="#h2__513033242048165810" id="h2__513033242048165810"></a>

* Manual Discretization is one type of Discretization available in [Step 4 — Discretization and Aggregation](../) of the Data Import Wizard.

### Manual Discretization

* Select Manual from the drop-down menu.
* Several additional items and buttons appear on the left side, plus a Cumulative Distribution Function (CDF) is shown on the right. This CDF plot can help in selecting appropriate discretization intervals.&#x20;
* In the screenshot below, the variable Standing Height (cm) is selected, meaning that the CDF plot corresponds to that variable.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689861969/DataImportWizard-4-DiscretizationManual_rtjmpu.png" alt=""><figcaption></figcaption></figure>

* Click on the Density Function button, and the Probability Density Function (PDF) of the same variable appears.
* Now the button reads Distribution Function, and by clicking it, you can toggle back to the CDF view.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689863072/DataImportWizard-4-DiscretizationManualPDF_obdetr.png" alt=""><figcaption></figcaption></figure>

* By default, only one threshold is placed at the mean value of the corresponding variable.
* This threshold appears as a horizontal line on the CDF and a vertical line on the PDF.
* The CDF and PDF plots are interactive; you can add, delete, and modify thresholds.

#### Editing Thresholds <a href="#h3__844958102048165810" id="h3__844958102048165810"></a>

The following instructions apply to both plots:

* To select a threshold, left-click on that threshold.
* The selected threshold is highlighted in red.
* The remaining thresholds on the plot remain blue.
* The precise numerical value of a selected threshold is shown in the Threshold Value field to the right of the plot.
* To move a threshold, click on it and hold, then move it. Release to fix its position.
* The percentages displayed at the end of a selected threshold refer to the share of observations that fall into the intervals above and below this threshold.
* Instead of moving the selected threshold with your cursor, you can type a specific value into the Threshold Value field.
* To add an additional threshold, right-click with your cursor on the desired position.
* To remove an existing threshold, right-click on it to delete it.
* A zoom function is available for examining the plot in detail:&#x20;
  * Hold the `Ctrl` key, click and hold the left mouse button, then move the cursor across the range you wish to focus.
    * To revert to the default zoom, hold `Ctrl`, then double-click anywhere in the plot area.
    * You can zoom in repeatedly until you have reached the desired magnification level.&#x20;
* As an alternative to selecting a threshold by left-clicking, you can scroll through all thresholds using the Previous and Next buttons.&#x20;

Note that as soon as a threshold is defined on a Continuous variable, it is considered Discretized, and the variable's data column is colored in soft blue.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689863786/ManualDiscretization2_rlyrrs.svg" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
The interactive CDF and PDF plots are similar to the editing functions available under Curve View in the Node Editor.
{% endhint %}

### Workflow Illustration <a href="#h4__18435112832048165810" id="h4__18435112832048165810"></a>

We re-use the dataset from the previous steps, so we can fast-forward to Step 4 and focus on that step.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689864311/DataImportWizard-4-DiscretizationManual_mtahgb.mp4" %}

### Generate a Discretization <a href="#h4__18435112832048165810" id="h4__18435112832048165810"></a>

* While remaining on the Manual Discretization screen, you can also utilize the Generate a Discretization function.
* It allows you to use the algorithms from [Automatic Discretization](about:blank/data-import-wizard-discretization-aggregation-discretization.html#h3\_\_1843511283\_1116736482) but in a more controlled environment where you can closely observe the results of the Discretization.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689864404/DataImportWizard-4-DiscretizationManualPDF_fpujpb.png" alt=""><figcaption></figcaption></figure>

* Click on the Generate a Discretization button.
* Then, select the Type from the drop-down menu, e.g., the R2-GenOpt algorithm.\
  You have nine algorithms available, i.e., the univariate methods only.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689864499/DataImportWizard-4-ManualGenerateDiscretization_ln2dul.png" alt=""><figcaption></figcaption></figure>

* Choose the number of Intervals, e.g., 5.&#x20;
* Set a Minimum Interval Weight, which defines the minimum prior probability of an interval in percent. The default value is 1%.
* Note that you can set defaults for the above settings under `Main Menu > Window > Preferences > Discretization`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689864626/Discretization_ho5elj.png" alt=""><figcaption></figcaption></figure>

* Additionally, there are options for Log Transformation and Isolate Zeros, which we discuss in the context of Automatic Discretization.
* Click OK to perform the Discretization.

### Workflow Illustration <a href="#h2_17419452512048165810" id="h2_17419452512048165810"></a>



{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689864741/DataImportWizard-4-DiscretizationManualGenerateDiscretization_bnanxv.mp4" %}

### Transfer the Discretization Thresholds <a href="#h2_14942465262048165810" id="h2_14942465262048165810"></a>

In certain situations, you may carefully choose thresholds for a variable (see [Manual Discretization Workflow Animation](about:blank/data-import-wizard-discretization-manual-discretization.html#h4\_\_1843511283\_445076046)). Perhaps another variable, or multiple variables, should have exactly the same discretization. In this context, you can use the Transfer the Discretization Thresholds button.

* Select the source variable from which you wish to copy the thresholds.
* Click the Transfer the Discretization Thresholds button.&#x20;
* A new window opens up that allows you to select one or more target variables.
* Select the target variables.
* Click OK.

### Workflow Animation <a href="#h3_6009465172048165810" id="h3_6009465172048165810"></a>

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689864845/DataImportWizard-4-DiscretizationManualTransferDiscretizationThresholds_s4zzag.mp4" %}

### Create a Class for Each Type of Discretization <a href="#h2_8956455102048165810" id="h2_8956455102048165810"></a>

* This checkbox is synchronized across Manual and Automatic Discretization processes.
* If checked, BayesiaLab automatically creates Classes for each type of Discretization, i.e., all variables that are discretized with the same algorithm will belong to the same Class.
* Note that variables that were discretized manually, even if you used the Generate a Discretization button, will all become members of the Class MANUAL.
* You can review the Class memberships in the Class Editor after the data import process is complete.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689864929/ClassEditorDiscretizationClasses_mhltp3.png" alt=""><figcaption></figcaption></figure>

### Load Discretizations <a href="#h2_11317778012048165810" id="h2_11317778012048165810"></a>

* This function allows you to load a Discretization Dictionary with saved Discretization Intervals and Discretization Methods.
* This approach is particularly helpful when you repeatedly import datasets with the same variables for which you have already found a suitable discretization.

The following text file illustrates the syntax of a Discretization Dictionary.

| Discretization Dictionary                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code>Age=R2_GENETIC_OPTIMIZATION 5 0.01
Weight\ (kg)=MANUAL 50 60 70 80 90 100 125 150 200
Standing\ Height\ (cm)=MANUAL 150 160 170 180 190
Body\ Mass\ Index=MANUAL 15 20 25 30 35 40
Waist\ Circumference\ (cm)=R2_GENETIC_OPTIMIZATION 5 0.01
Hip\ Circumference\ (cm)=R2_GENETIC_OPTIMIZATION 5 0.01
Upper\ Leg\ Length\ (cm)=R2_GENETIC_OPTIMIZATION 5 0.01
Upper\ Arm\ Length\ (cm)=R2_GENETIC_OPTIMIZATION 5 0.01
Arm\ Circumference\ (cm)=R2_GENETIC_OPTIMIZATION 5 0.01
</code></pre> |
