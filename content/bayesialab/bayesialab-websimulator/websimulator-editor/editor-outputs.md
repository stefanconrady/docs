# Editor — Outputs

### Outputs&#x20;

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/35651863/35651917.png" alt="" width="375"><figcaption></figcaption></figure>

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184179/BayesiaLab\_Icons/number\_1\_hgld3u.svg) **Available Nodes** &#x20;

This list displays the Available Nodes in the current Bayesian network that can be used as Inputs or Outputs in the WebSimulator of the network. &#x20;

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184180/BayesiaLab\_Icons/number\_2\_hzb4in.svg) **Available Metrics**&#x20;

This list shows the Available Metrics that can be used as Outputs in the WebSimulator of the network.

{% hint style="info" %}
The panels for Available Nodes and Available Metrics appear identically in all three tabs of the WebSimulator Editor, i.e., Simulator, Inputs, and Outputs.
{% endhint %}

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184180/BayesiaLab\_Icons/number\_3\_jcb1hs.svg) **Outputs**&#x20;

This panel displays the nodes that are selected to be published as Outputs in the WebSimulator.

* To add nodes or metrics as Output Components, you select the nodes or metrics on the Available Nodes or Available Metrics lists and then drag and drop them onto the Outputs panel.
* You can remove an item from the Outputs panel by dragging it back to its origin.
* You can reorder the list items by dragging them to the desired positions on the list. The specified order will be retained in the WebSimulator display.
* As you drop nodes or metrics onto the Outputs list, you will be prompted to select the appearance of their corresponding components in the WebSimulator. The options depend on the type of node or metric:
  * Probabilistic Node — Display Options:
    * Mean Bar
    * Mean Gauge
    * Probability Bar
    * Probability Text
  * Utility Node — Display Options:
    * Utility Bar
    * Utility Gauge
    * Utility Text
  * Joint Probability Metric — Display Options:
    * Joint Probability Bar
    * Joint Probability Gauge&#x20;
    * Joint Probability Text
  * Global Utility Metric — Display Options:
    * Global Utility Bar
    * Global Utility Gauge
    * Global Utility Text
  * Decision Node:
    * Quality Bar
  * Function Node
    * Function

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184182/BayesiaLab\_Icons/number\_4\_x5kvw0.svg) **Displayed Name**&#x20;

The Displayed Name specifies the component's name label in the WebSimulator. By default, it is the name of the node or the metric.

Clicking the Long Name button adopts any Long Name that you may have defined for the node when editing the network in BayesiaLab.

You can also edit the Displayed Name.

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184184/BayesiaLab\_Icons/number\_5\_asbpka.svg) **Font Color**&#x20;

* Font Color specifies the color of the Displayed Name in the WebSimulator.

&#x20;![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184185/BayesiaLab\_Icons/number\_6\_ymshzl.svg) **Component Image**&#x20;

* Component Image allows you to select an image or icon to display with the component. By default, any image already associated with the node in BayesiaLab will be used.

&#x20;![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184185/BayesiaLab\_Icons/number\_7\_mer83u.svg) **Image Size**&#x20;

* Image Size — The image displayed in the component is square, and you can specify the length of the square's sides in pixels.

&#x20;![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184185/BayesiaLab\_Icons/number\_8\_dz7b0o.svg) **Number Output Format**&#x20;

* Clicking on Number Output Format, you can specify the number format of all components, with the exception of the Function Nodes.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Editor/Editor-Outputs/NumberFormat.png)

**Output Format for Function Node**&#x20;

*   If a Function Node is selected as an Output component, a separate Output Format button allows you to set the number format separately from the other components. By default, the Function Node component adopts the number format defined in the Properties tab of the Function Node Editor.\


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Editor/Editor-Outputs/FunctionNodeFormat.png" alt="" width="375"><figcaption></figcaption></figure>

&#x20;![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184186/BayesiaLab\_Icons/number\_9\_lftuym.svg) **Description** &#x20;

* The Description field provides you with space for additional information regarding the output component. The published WebSimulator displays this content when end-users hover with their cursor over the component. By default, Description adopts the Comment you may have added to the node while editing the network in BayesiaLab.

**Preview**&#x20;

* The Preview button opens up a static preview of the WebSimulator in your default web browser to let you see its appearance before publishing it. This lets you quickly fine-tune the layout and experiment with various component settings.

{% hint style="info" %}
The Preview is static and does not perform any simulation. While you can experiment with the inputs, the output side of the WebSimulator will not update.
{% endhint %}

**Reset Button**&#x20;

* A reset button ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184130/BayesiaLab\_Icons/default\_qmy82k.svg) is available for most settings. Click it to return to the default value.&#x20;
