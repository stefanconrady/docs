# Using the Adaptive Questionnaire

### Opening an Adaptive Questionnaire&#x20;

*   For end-users, there are three ways to reach the page of an Adaptive Questionnaire:

    * Open a web browser and go to [https://simulator.bayesialab.com/#!questionnaire](https://simulator.bayesialab.com/#!questionnaire)
      * Only models that were published using a public account will appear in the drop-down menu.
      * Select any available models from the drop-down menu to open it.\


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/AdaptiveQuestionnaireSelection.png" alt=""><figcaption></figcaption></figure>

    * You open a specific URL in the format `https://simulator.bayesialab.com/#!questionnaire/Identifier` and directly go to that particular Adaptive Questionnaire page.
      * A public Adaptive Questionnaire page opens immediately.
      * A private Adaptive Questionnaire page prompts you for a password.
    * On the WebSimulator homepage at [https://simulator.bayesialab.com](https://simulator.bayesialab.com/), click the navigation icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/sitemap\_ru1kev.svg), then select Go To Adaptive Questionnaire ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/edit\_gcnvuf.svg).

### Adaptive Questionnaire Page&#x20;

* Upon opening the page of the selected model, you see the layout specified by the designer of the Adaptive Questionnaire.
* The Adaptive Questionnaire features three panels:
  * The Open Questions Panel (top left) shows the unobserved variables according to their importance with regard to the Targets.
  * The Answered Questions Panel (bottom left) lists all the variables that have been observed or intentionally skipped.
  * The Output Panel (right) features the Targets, i.e., the variables of interest that we wish to predict.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/AdaptiveQuestionnairePanels2.png" alt=""><figcaption></figcaption></figure>

### Adaptive Questionnaire Selector&#x20;

* At the top of the Open Questions Panel, a drop-down menu offers you other available Adaptive Questionnaires to which you can switch at any time by clicking on the corresponding list item.
* Selecting the first (blank) item in the list closes your current Adaptive Questionnaire and loads a blank page.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/QuestionnaireSelection.gif" alt=""><figcaption></figcaption></figure>

#### Adaptive Questionnaire Information&#x20;

* To the right of the Adaptive Questionnaire Selector, there are two icons:
  * Clicking on the information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) brings up the Description of the current Adaptive Questionnaire.
  * Clicking on the eye icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184056/BayesiaLab\_Icons/eye\_rs46m5.svg) displays the Image associated with the current Adaptive Questionnaire.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/QuestionnaireInformation.gif" alt=""><figcaption></figcaption></figure>

### Open Questions Panel (Input Panel)&#x20;

* The order of the Inputs in the panel — left-to-right, top-to-bottom — indicates the optimal sequence in which the "open questions" should be answered.
* More specifically, the information gain determines the sort order — from high to low — each Input brings towards the Targets.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/OpenQuestionPanel.png" alt=""><figcaption></figcaption></figure>

### **Setting Evidence: Answering and Skipping Questions**&#x20;

* You enter an observation, i.e., a piece of evidence, by changing the state, the value, or the slider position of an Input.
* Immediately upon entering your evidence, the corresponding Input is marked Observed and moved to the Answered Questions Panel below.
* The evidence is applied to the corresponding node in the underlying Bayesian network, which computes the posterior probability distributions of Inputs and Targets. Their updated distributions are displayed instantly.
* Furthermore, the information gain of the Inputs is recalculated, and their order is updated dynamically in the Open Questions Panel.
* If you cannot answer the most relevant question, as suggested by the Input position, you can skip this question by clicking the icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184199/BayesiaLab\_Icons/arrow-right\_izur62.svg).
* Skipping a question will move the corresponding Input to the Answered Questions Panel below.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/SettingEvidence.gif" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note that despite the recommended order, you can still set evidence on any Inputs in any order.
{% endhint %}

### **Costs**&#x20;

* Ordering the Inputs also takes into account any so-called Costs of observing a variable.
* In BayesiaLab, Cost captures the "price to pay" to obtain an observation. In the medical domain, for instance, measuring the blood pressure of a patient is presumably less expensive than performing an electrocardiogram. Cost could refer to an actual monetary amount of observing a specific Input or merely express a relative cost, e.g., it requires twice as much effort/time/resources to observe X than to observe Y.

{% hint style="info" %}
All Costs are defined in the underlying Bayesian network and cannot be modified by the end-user of the Adaptive Questionnaire.
{% endhint %}

### **Modifying and Removing Evidence**&#x20;

* Once an Input has been observed and moved to the Answered Questions panel, you can still modify the evidence on that Input.
* Alternatively, you can remove an observation altogether by unchecking the Observed box on the Input. In that case, the input moves back to the Open Questions Panel.
* Clicking the eraser icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/eraser\_s9i9mt.svg) removes all pieces of evidence that you have set on the Inputs.
* As a result, all Inputs move back up to the Open Questions Panel.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/RemoveEvidence.gif" alt=""><figcaption></figcaption></figure>

### Display Variations&#x20;

* To highlight the impact of your observations on the Output, you have to select the option Display Variations available by clicking the Options icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the upper right corner of the page.
* Now, the Outputs display the changes that resulted from setting the most recent piece of evidence.
* The deltas are shown in green and red for positive and negative changes respectively.
* For gauge-style Outputs, the variations are also highlighted with green and red arcs for positive and negative impacts, respectively.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845129.png)![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714048/12845128.png)
* By default, the variations are calculated with respect to the previous state, i.e., before setting the most recent observation.
* This shows the incremental change brought to the Outputs by each piece of evidence.
* However, if you are interested in the impact of a set of multiple observations, you first need to set a reference state:
  * Click the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) to open the Options drop-down menu.
  * Select `Store Reference State` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184200/BayesiaLab\_Icons/bookmark-o\_osaa0u.svg).
* The deltas shown on the Outputs now are calculated based on the Reference State.

### Observation Sets&#x20;

* Observations Sets allow you to save sets of evidence so you can retrieve and review them later, without having to enter each observation again individually.
* You can also share your saved Observation Sets with other end-users for their review.
* Furthermore, BayesiaLab users can save their Observation Sets, such as the best solutions from an optimization performed with BayesiaLab, and share them with Adaptive Questionnaire users so they can review the Observation Sets that are proposed as optimal solutions.  &#x20;
* At any time in the Adaptive Questionnaire, you can save the state of observations as an Observation Sets. This even includes non-evidence, i.e., Inputs that have not been observed. Thus, your Observation Sets can include observed and not-observed Inputs.

### **Storing an Observation Set**&#x20;

* To save an Observation Set, click the plus icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/plus-circle\_zrnmlk.svg) from the Icon Bar.
* A pop-up window prompts you to specify a name for the to-be-stored Observation Set.
* Enter the name and click OK.
* Now, an additional icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184201/BayesiaLab\_Icons/chevron-circle-down\_xtohaz.svg) in the Icon Bar indicates the presence of your saved Observation Set.&#x20;
* The new Observation Set is like a running tab to which you can add further observations under the same Observation Set Name.
* Click the Plus icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184218/BayesiaLab\_Icons/plus-circle\_zrnmlk.svg) again, and you can add to the same Observation Set Name or create a new Observation Set Name.
* If you select an existing Observation Set Name, the evidence you save will be sequentially numbered, starting with 0.

### **Retrieving an Observation Set**&#x20;

* ​If you click on the Observation Set icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184201/BayesiaLab\_Icons/chevron-circle-down\_xtohaz.svg) in the Icon Bar​, a drop-down menu lists all saved Observation Sets with their name and sequence number.
* Click on the Observation Set you wish to restore, and the Adaptive Questionnaire sets all observations accordingly and performs inference on that basis.

{% hint style="warning" %}
It is important to realize that the Adaptive Questionnaire is not merely returning saved results. Instead, the Adaptive Questionnaire only retrieves the saved Inputs and then performs inference again on that basis. Hence, all results shown are freshly recalculated.
{% endhint %}

### **Clearing Observation Sets**&#x20;

* You can clear all Observation Sets that are currently stored in your Adaptive Questionnaire session.
* Click the gear ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) icon, then select `Observations > Clear Stored Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184205/BayesiaLab\_Icons/eraser\_s9i9mt.svg).

### **Saving a Scenario File**&#x20;

* By default, your stored Observations Sets only remain available during your current Adaptive Questionnaire session. If you closed your browser and reopened the same Adaptive Questionnaire again, all Observation Sets would be gone.
* To save Observation Sets permanently, you can export them to a Scenario File.
* Click on the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select `Observations > Export Stored Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/download\_e0evqh.svg).&#x20;
* Once you confirm, your browser saves a file named `observations.txt` to your local drive.
* This file can be shared with other WebSimulator and BayesiaLab users so they can retrieve and replicate your saved Observation Sets.

{% hint style="info" %}
The format of this Scenario File is identical to the Evidence Scenario File produced by BayesiaLab. As such, it is an ideal format for exchanging scenarios for review and discussion between BayesiaLab users and WebSimulator users.
{% endhint %}

### **Loading a Scenario File**&#x20;

* Similarly, you can load a locally saved Scenario File back into the Adaptive Questionnaire.
* Click on the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select `Observations > Import Observations` ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184058/BayesiaLab\_Icons/upload3\_g4icj8.svg).

{% hint style="warning" %}
Please note the important distinction between temporarily storing an Observation Set for the duration of your WebSimulator session and permanently saving an Observation Set to an external Scenario File on a local drive.
{% endhint %}

### **Simulation Mode**&#x20;

* Whenever you have stored Observation Sets available in your Adaptive Questionnaire — indicated by the Observation Set icon  — you can enter the so-called Simulation Mode. This mode allows you to easily scroll through all available Observation Sets.
* Click on the gear icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) in the Icon Bar, then select Simulation Mode ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184206/BayesiaLab\_Icons/film\_hhxpef.svg).
* With the Simulation Mode activated, the Icon Bar features two additional icons as scroll buttons: ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184202/BayesiaLab\_Icons/chevron-circle-left\_kdfydu.svg)![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/chevron-circle-right\_j8vqkq.svg). &#x20;
* You can now step through all Observation Sets backward and forward.&#x20;
* The name of the current Observation Set is shown on a slide-in label in the bottom right corner of your Adaptive Questionnaire window.
* You can further modify any Observation Set retrieved in that fashion; however, you can't save that modified evidence as a new Observation Set. To do so, you will first need to exit the Simulation Mode.

### Layout&#x20;

* Beyond the default layout specified by the publisher of the Adaptive Questionnaire, you can choose your own layout to optimize the Adaptive Questionnaire of your screen size, resolution, and format.
* ​You can choose the layouts separately for the Input and the Output panel, but the options are the same for both.
* Click the gear ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184204/BayesiaLab\_Icons/cog\_koomse.svg) icon, then select `Layout > Input or Layout > Output` and pick the desired layout for each panel:
  * ​Input refers to the Open Questions Panel.
  * History refers to the Answered Questions Panel.
  * Output refers to the Output Panel.

#### Flow ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184210/BayesiaLab\_Icons/lines\_ojztw1.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/FlowLayout.png" alt=""><figcaption></figcaption></figure>

#### Grid ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184207/BayesiaLab\_Icons/grid-small\_cdvhr3.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/GridLayout.png" alt=""><figcaption></figcaption></figure>

#### Line ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184199/BayesiaLab\_Icons/align-left\_j6znrf.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/LineLayout.png" alt=""><figcaption></figcaption></figure>

#### Accordion ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184198/BayesiaLab\_Icons/accordion-menu\_fu41vs.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-End-User-Guide/Using-the-Adaptive-Questionnaire/AccordionLayout.png" alt=""><figcaption></figcaption></figure>
