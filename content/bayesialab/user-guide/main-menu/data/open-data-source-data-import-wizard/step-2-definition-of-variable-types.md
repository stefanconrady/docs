# Step 2 — Definition of Variable Types

### Context <a href="#h2__1212884521627883848" id="h2__1212884521627883848"></a>

* In Step 2 — Definition of Variable Types of the five-step Data Import Wizard, you need to define variable types.
* Step 2 contains four panels that relate to each other in their content and available actions.

### Overview of Elements in Step 2 <a href="#h2__772583257627883848" id="h2__772583257627883848"></a>

* [Type](step-2-definition-of-variable-types.md#h2\_1421152990627883848)
* [Multiple Typing](step-2-definition-of-variable-types.md#h2\_559375293627883848)
* [Information](step-2-definition-of-variable-types.md#h2\_\_2101430728627883848)
* [Data](step-2-definition-of-variable-types.md#h2\_2620942627883848)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689809905/DataImportWizard-2_az6zdp.gif" alt=""><figcaption></figcaption></figure>

### Type <a href="#h2_1421152990627883848" id="h2_1421152990627883848"></a>

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1689809944/DataImportWizard-2-TypePanel\_lj0l6i.png)

* With the radio buttons in the Type panel, you can define the type of each variable.
* Before you start making your determinations, BayesiaLab has already made some guesses regarding the appropriate variable type, i.e., Discrete versus Continuous.
* Furthermore, some variables have limited options regarding the variable type because of their distributions:
  * If a variable has the same value for all observations, it falls into the Unused variable type. Such a not-distributed variable cannot be imported at all into BayesiaLab.
  * Variables that contain any text values cannot be declared Continuous variables.
  * Variables with Missing Values cannot be of the type Weight, Row Identifier, or Learn/Test.

#### Usage <a href="#h2_519852009627883848" id="h2_519852009627883848"></a>

* To select a variable, click on the variable header or click anywhere inside the column in the [Data](about:blank/data-import-wizard-definition-variable-types.html#h2\_2620942\_1387816040) panel.
* You can perform the selection of multiple variables with keystroke combinations commonly used in spreadsheet editing:
  * `Ctrl+Click`: add a variable to the current selection.
  * `Shift+Click`: add all variables between the currently selected and the clicked variable to the selection.
  * `Ctrl+A`: select all variables in the [Data](about:blank/data-import-wizard-definition-variable-types.html#h2\_2620942\_1387816040) panel.
  * `Shift+End`: select all variables from the currently selected variable to the rightmost variable in the table.
  * `Shift+Home`: select all variables from the currently selected variable to the leftmost variable in the table.&#x20;
* The current selection is highlight by showing the selected columns in a darker shade of their current color.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689810228/DataImportWizardStep2Colors_kov54x.svg" alt=""><figcaption></figcaption></figure>

**Discrete**

* The Discrete type considers each unique value of the variable a distinct state.
* Any variable that contains text will be considered Discrete by default.
* The maximum number of unique values that can be accommodated can be specified under `Main Menu > Window > Preference > Editing > Node > Maximum Number of States`.

**Continuous**

* The Continuous type applies to numerical variables, which must be discretized in Step 4 — Discretization and Aggregation.
* If a variable contains integer values above a certain threshold, the variable will be considered Continuous.&#x20;
* You can specify this threshold under `Main Menu > Windows > Preferences > Data > Import & Associate > Threshold for Assuming Integers as Continuous`. The default threshold value is 5.

{% hint style="info" %}
Learn more about Discrete and Continuous nodes in the Node Editor topic.
{% endhint %}

**Weight**

Weighting is often applied to surveys to make a survey sample representative of the demographics of the underlying population.

* If your dataset contains such a Weight variable, select it by clicking on the corresponding column.
* Then, select the Weight button in the Type panel.
* Later, in Step 4 — Discretization and Aggregation, you can specify whether or not to normalize the Weight variable.

**Learning/Test**

For a dataset that has already been split into a Learning Set and a Test Set, you can use such an existing definition to import your data into BayesiaLab.

* Both the Learning Set and the Test Set need to be in the same data table, rather than in separate files.
* A binary indicator variable needs to identify each set with a unique code.
* With a Learning/Test variable defined, in Step 4 — Discretization and Aggregation of the Data Import Wizard, you need to assign which of your codes corresponds to BayesiaLab's Learning and Test states.\


**Row Identifier**

You can assign one or more variables to serve as Row Identifiers. The values of Row Identifiers are imported but not processed in any way. They serve as labels that are attached to each record.

* There are numerous functions in BayesiaLab that allow you to look up what record in the dataset corresponds to what is currently on display on the screen.
* For instance, Automatic Evidence-Setting displays the Row Identifier in the Status Bar.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689810402/StatusBarRowIdentifier_eryqco.png" alt=""><figcaption></figcaption></figure>

#### Unused <a href="#h3__426962452627883848" id="h3__426962452627883848"></a>

By selecting the Unused button, you can skip the import of the selected variables. In previous versions of BayesiaLab, this option was also known as "Not Distributed."

* Unused is automatically applied to variables containing only a single value across all observations, i.e., when the variable is "not distributed," hence the original name.&#x20;
* Unused variables will appear grayed out in the remaining steps of the Data Import Wizard.

### Multiple Typing <a href="#h2_559375293627883848" id="h2_559375293627883848"></a>

The Multiple Typing panel allows you to quickly assign variable types across multiple variables.

* Click Set All to Discrete to apply the [Discrete](about:blank/data-import-wizard-definition-variable-types.html#h4\_\_1490462369\_1387816040) type all variables, if possible.
* Click Set All to Continuous to apply the [Continuous](about:blank/data-import-wizard-definition-variable-types.html#h4\_1079482845\_1387816040) type all variables, if possible.

{% hint style="warning" %}
By clicking either button, all previous type assignments are replaced.
{% endhint %}

You can automatically remove variables, i.e., set them to the Unused type, if they exceed a certain column percentage of Missing Values.

* Click the Set Missing Values Threshold button.
* From the pop-up window, set the percentage.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689810584/DataImportWizard-2-MultipleTypingFilterColumns_okyyso.png" alt=""><figcaption></figcaption></figure>

* All variables that exceed the specified threshold are set to Unused.

### Information <a href="#h2__2101430728627883848" id="h2__2101430728627883848"></a>

The Information panel provides a range of statistics relating to the current type assignment of variables:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689810517/DataImportWizard-2-InformationPanel_kwsnfq.png" alt=""><figcaption></figcaption></figure>

* Number of Rows refers to the number of records in the to-be-imported datasets. In the context of datasets, rows, records, cases, samples, and observations all have equivalent meanings.&#x20;
* Discrete shows the absolute count of variables currently assigned to the [Discrete](about:blank/data-import-wizard-definition-variable-types.html#h4\_\_1490462369\_1387816040) type. The percentage refers to the proportion of Discrete variables among all variables, including the type Unused.
* Continuous shows the absolute count of variables currently assigned to the [Continuous](about:blank/data-import-wizard-definition-variable-types.html#h4\_1079482845\_1387816040) type. The percentage refers to the proportion of Continuous variables among all variables, including the type Unused.
* Others displays the count of all the variable assigned to the types Row Identifier, Weight, or Learn/Test.
* Unused shows the absolute count of variables currently assigned to the Unused type. The percentage refers to the proportion of Unused variables among all variables.
* Missing Values displays the count of cells in the dataset that contain Missing Values. The percentage refers to the proportion of cells in the dataset that contain Missing Values, including all variables types, even Unused, Row Identifier, and Learning/Test.
* Filtered Values displays the count of cells in the dataset that contain Filtered Values, as indicated by the asterisk (\*).​ The percentage refers to the proportion of cells in the dataset that contain Filtered Values, including all variable types, even Unused, Row Identifier, and Learning/Test.

### Data <a href="#h2_2620942627883848" id="h2_2620942627883848"></a>

* The Data panel visualizes the current variable selection and type assignment with colors (see [Usage](about:blank/data-import-wizard-definition-variable-types.html#h2\_519852009\_1387816040) above).
* Horizontal and vertical scrolling allows you to view the entire dataset that will be imported.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689810658/DataImportWizard-2-DataPanel_i5gew4.png" alt=""><figcaption></figcaption></figure>

### Workflow Animation <a href="#h2_1165600711627883848" id="h2_1165600711627883848"></a>

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689810717/DataImportWizard-2_rgknhh.mp4" %}
