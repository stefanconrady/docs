# Class Description Generator

### Context

* To manage groups of nodes, BayesiaLab offers Classes.&#x20;
* Nodes can be added to Classes manually or automatically. For instance, the Variable Clustering function can assign nodes to new Classes representing latent factors. By default, newly-created Classes have generic names, such as \[Factor\_0], which carries no meaning.
* Finding suitable descriptions for Classes can be time-consuming.
* The Class Description function can assist you in finding meaningful summaries of a Class of nodes.

### Using Class Description Generator for Groups of Nodes

* With the Hellixia Class Description Generator, we can quickly find a useful description for a subset of nodes we select.
* In our example, we have a large number of nodes from an auto buyer satisfaction survey.&#x20;
* We are interested in a subset of nodes related to the quality perception of the vehicle interior, i.e.:
  * Interior Colors
  * Quality of Interior Materials
  * Interior Trim & Finish
  * Quality of Seat Materials
* Select these nodes node of interest.&#x20;
* Then select `Main Menu > Hellixia > Class Description`.
* Specify a Context, if applicable.
* Indicate by ticking the checkboxes where the subject matter is stored, i.e., Node Name, Node Long Name, or Node Comment. Check all that apply.
* Clicking OK starts generating the Class Description.
* The chime confirms when the process is complete.
* Opening the Class Editor shows the Class Description that was generated.
* Select `Graph Contextual Menu > Edit Classes`
* The Description column shows the newly-generated Class Description.

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689096292/ClassDescriptionOfNodes_cg3kh5.mp4" %}

### Using the Class Description Generator from within the Class Editor

* BayesiaLab's Clustering function produces new Factors and associated Classes.&#x20;
* So, having a dozen or more new Classes is quite common in this context.
* By default, the newly-generated Classes have generic and non-informative names, like \[Factor\_0], \[Factor\_1], etc.
* Given that the Factors and Classes are meant to represent meaningful concepts, naming them is important but can be tedious.
* In the following example, 57 Factors (and Classes) were created from 240 manifest nodes. Each manifest node measures the degree of agreement or disagreement with statements in a personality test, such as, "I get angry easily" or "I remain calm under pressure."
* These original statements are included as Node Comments with every node.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689105644/NodeComments_vwm2rv.webp" alt=""><figcaption></figcaption></figure>

### Workflow Illustration

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689267834/Class-Descriptions_ikqr8x.mp4" %}

