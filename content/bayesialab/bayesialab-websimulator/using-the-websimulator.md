# Using the WebSimulator

### Opening a WebSimulator&#x20;

* For end-users, there are three ways to reach a WebSimulator page:
  * Open a web browser and go to the WebSimulator homepage at [https://simulator.bayesialab.com](https://simulator.bayesialab.com/)
    * In the header, you can filter by Field of Study, Analysis Type, and Model Type.
    * Only models that were published using a public account will appear here.
    * Click on any of the available models to open them.
  * You open a specific URL in the format `https://simulator.bayesialab.com/#!simulator/Identifier` and directly go to that particular WebSimulator page.
    * A public WebSimulator page opens immediately.
    * A private WebSimulator page prompts you for a password.
  * On the WebSimulator homepage at [https://simulator.bayesialab.com](https://simulator.bayesialab.com/), click the navigation icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/sitemap\_ru1kev.svg) in the Icon Bar, then select Go to Simulator ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184219/BayesiaLab\_Icons/sliders\_tecnu0.svg).​

### WebSimulator Page&#x20;

* Upon opening the page of the selected model, you see the layout specified by the designer of the WebSimulator.
* The WebSimulator features two panels:
  * Input Panel (left)
  * Output Panel (right)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714041/12845094.png" alt=""><figcaption></figcaption></figure>

### WebSimulator Selector&#x20;

* At the top of the Input Panel, a drop-down menu offers you other available WebSimulators, which you can switch to at any time by clicking on the corresponding list item.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845118.png" alt=""><figcaption></figcaption></figure>

* Selecting the first (blank) item in the list closes your current WebSimulator and loads a blank page.

### WebSimulator Information&#x20;

* To the right of WebSimulator Selector, there are two icons:
  * Clicking on the information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) brings up the Description of the current WebSimulator.
  * Clicking on the eye icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184056/BayesiaLab\_Icons/eye\_rs46m5.svg) displays the Image associated with the current WebSimulator.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-WebSimulator/WebSimulatorInformation.gif" alt=""><figcaption></figcaption></figure>

### Setting Observations/Evidence

{% hint style="info" %}
Please note that we use "observation" and "piece of evidence" as well as "setting evidence," "setting observations," and "observing" interchangeably.
{% endhint %}

* Depending on the type of Input, you can set an observation in a number of ways:
  * Moving a slider\
    ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-WebSimulator/SetEvidenceSlider.gif)\

  * Selecting an item from a drop-down menu\
    ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-WebSimulator/SetEvidenceDropdown.gif)\

  * Selecting a switch\
    ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-WebSimulator/SetEvidenceSwitch.gif)\

  * Typing in a numeric value\
    ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-WebSimulator/SetEvidenceText.gif)\

* Upon setting evidence on an Input, the Observed checkbox under the corresponding Input is checked.
* With that, this new evidence is set to the node in the underlying Bayesian network, which computes the posterior probability distributions of all other nodes in the network.
* As a result, the WebSimulator displays updated Inputs and Outputs.

{% hint style="info" %}
Note that a Bayesian network always performs omnidirectional inference, so new evidence can affect all nodes, not just the Outputs (see What is a Bayesian Network? Probabilistic Inference)
{% endhint %}

* There are two ways to remove any evidence you have set:
  * You click the Eraser icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/eraser\_s9i9mt.svg) in the upper right corner of the page. This erases all pieces of evidence set thus far.
  * Alternatively, you can remove the evidence set on an individual Input by unchecking the Observed box.

### Display Variations&#x20;

* To highlight the impact of your observations on the Outputs, you have to select the option `Display Variations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/exchange\_ldftlk.svg) available by clicking the Options icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the upper right corner of the page.
* Now, the Outputs display the changes that resulted from setting the most recent piece of evidence.
* The deltas are shown in green and red for positive and negative changes respectively.
* For gauge-style Outputs, the variations are also highlighted with green and red arcs for positive and negative impacts, respectively.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845129.png)![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845128.png)
* By default, the variations are calculated with respect to the previous state, i.e., before setting the most recent observation.
* This shows the incremental change brought to the Outputs by each piece of evidence.
* However, if you are interested in the impact of a set of multiple observations, you first need to set a reference state:
  * Click the Gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) to open the Options drop-down menu.
  * Select `Store Reference State`.
* The deltas shown on the Outputs now are calculated based on the Reference State ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184200/BayesiaLab\_Icons/bookmark-o\_osaa0u.svg).

### Observation Sets&#x20;

* Observations Sets allow you to save sets of evidence to retrieve and review them later without having to enter each observation again individually.
* You can also share your saved Observation Sets with other end-users for their review.
* Furthermore, BayesiaLab users can save their Observation Sets, such as the best solutions from an optimization performed with BayesiaLab, and share them with WebSimulator users so they can review the Observation Sets that are proposed as optimal solutions.  &#x20;
* At any time in the WebSimulator, you can save the state of observations as an Observation Set. This even includes non-evidence, i.e., Inputs that have not been observed. Thus, your Observation Sets can include observed and not-observed Inputs.

### **Storing an Observation Set**&#x20;

* To save an Observation Set, click the Plus icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/plus-circle\_zrnmlk.svg) from the Icon Bar.
* A pop-up window prompts you to specify a name for the to-be-stored Observation Set.
* Enter the name and click OK.
* Now, an additional icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184201/BayesiaLab\_Icons/chevron-circle-down\_xtohaz.svg) in the Icon Bar indicates the presence of your saved Observation Set.&#x20;
* The new Observation Set is like a running tab to which you can add further observations under the same Observation Set Name.
* Simply click the Plus icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/plus-circle\_zrnmlk.svg) again, and you can add to the same Observation Set Name or create a new Observation Set Name.
* If you select an existing Observation Set Name, the evidence you save will be sequentially numbered, starting with 0.

### **Retrieving an Observation Set**&#x20;

* ​If you click on the Observation Set icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184201/BayesiaLab\_Icons/chevron-circle-down\_xtohaz.svg) in the Icon Bar​, a drop-down menu lists all saved Observation Sets with their name and sequence number.
* Click on the Observation Set you wish to restore, and the WebSimulator sets all observations accordingly and performs inference on that basis.

{% hint style="warning" %}
It is essential to realize that the WebSimulator is not merely returning saved results. Instead, the WebSimulator only retrieves the saved Inputs and then performs inference again on that basis. Hence, all results shown are freshly recalculated.&#x20;
{% endhint %}

### **Clearing Observation Sets**&#x20;

* You can clear all Observation Sets that are currently stored in your WebSimulator session.
* Click the gear ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) icon, then select `Observations > Clear Stored Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/eraser\_s9i9mt.svg).

### **Saving a Scenario File**&#x20;

* By default, your stored Observations Sets only remain available during your current WebSimulator session. If you closed your browser and reopened the same WebSimulator again, all Observation Sets would be gone.
* To save Observation Sets permanently, you can export them to a Scenario File.
* Click on the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select `Observations > Export Stored Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/download\_e0evqh.svg).
* Once you confirm, your browser saves a file named `observations.txt` to your local drive.
* This file can be shared with other WebSimulator and BayesiaLab users so they can retrieve and replicate your saved Observation Sets.

{% hint style="info" %}
The format of this Scenario File is identical to the [Evidence Scenario File](../user-guide/main-menu/data/evidence-scenario-file/) produced by BayesiaLab. As such, it is an ideal format for exchanging scenarios for review and discussion between BayesiaLab users and WebSimulator users.
{% endhint %}

### **Loading a Scenario File**&#x20;

* Similarly, you can load a locally saved Scenario File back into the WebSimulator.
* Click on the Gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select `Observations > Import Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184058/BayesiaLab\_Icons/upload3\_g4icj8.svg).

{% hint style="warning" %}
Please note the important distinction between temporarily storing an Observation Set for the duration of your WebSimulator session and permanently saving an Observation Set to an external Scenario File on a local drive.
{% endhint %}

### **Simulation Mode**&#x20;

* Whenever you have stored Observation Sets available in your WebSimulator — indicated by the Observation Set icon  — you can enter the so-called Simulation Mode. This mode allows you to scroll through all available Observation Sets easily.
* Click on the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select Simulation Mode ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184206/BayesiaLab\_Icons/film\_hhxpef.svg).
* With the Simulation Mode activated, the Icon Bar features two additional icons as scroll buttons: ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184202/BayesiaLab\_Icons/chevron-circle-left\_kdfydu.svg)![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/chevron-circle-right\_j8vqkq.svg).
* You can now step through all Observation Sets backward and forward.&#x20;
* The name of the current Observation Set is shown on a slide-in label in the bottom right corner of your WebSimulator window.
* You can further modify any Observation Set retrieved in that fashion; however, you can't save that modified evidence as a new Observation Set. To do so, you will first need to exit the Simulation Mode.

### Layout&#x20;

* Beyond the default layout specified by the publisher of the WebSimulator, you can choose your own layout to optimize the WebSimulator of your screen size, resolution, and format.
* ​You can choose the layouts separately for the Input and the Output panel, but the options are the same for both.
* Click the gear ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) icon, then select `Layout > Input` or `Layout > Output` and pick the desired layout:

#### Flow ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184210/BayesiaLab\_Icons/lines\_ojztw1.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845131.png" alt="" width="375"><figcaption><p>Flow Layout</p></figcaption></figure>

#### Grid ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184207/BayesiaLab\_Icons/grid-small\_cdvhr3.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845132.png" alt="" width="375"><figcaption><p>Grid Layout</p></figcaption></figure>

#### Line ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184199/BayesiaLab\_Icons/align-left\_j6znrf.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845133.png" alt="" width="375"><figcaption><p>List Layout</p></figcaption></figure>

#### Accordion ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184198/BayesiaLab\_Icons/accordion-menu\_fu41vs.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845134.png" alt="" width="375"><figcaption><p>Accordion Layout</p></figcaption></figure>
