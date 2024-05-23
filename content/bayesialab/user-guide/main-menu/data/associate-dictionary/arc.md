# Arc

### Arc

To associate a Dictionary for Arc properties, select

`Main Menu > Data > Associate Dictionary > Arc >`

and then select the property from the submenu:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709412074/Associate-Dictionary-Arc_s9k69a.png" alt="" width="563"><figcaption></figcaption></figure>

* `Arcs`
  * Specifies the addition or removal of arcs for the currently active Bayesian network. If an arc removal is specified, it will precede any addition of an arc.
  * Before adding arcs, any constraints applicable to the active Bayesian network and the Temporal Indices will be checked. If a specified arc addition is inconsistent with the existing constraint, the arc won't be added.
  * Syntax Examples:
    * `N1->N2=`<mark style="color:green;">`true`</mark> adds an arc from N1 to N2
    * `N1->N2=`<mark style="color:red;">`false`</mark> removes the arc from N1 to N2
    * `N1<-N2=`<mark style="color:green;">`true`</mark> adds an arc from N2 to N1 (note the reversal of the arrow symbol `<-` produces an arc in the opposite direction).
    * Note that you need to add an escape character `\` before any spaces in node names. Otherwise, a space will be interpreted as a delimiter:\
      `N\ 1->Node\ 2=`<mark style="color:green;">`true`</mark> adds an arc from N 1 to N 2&#x20;
    * Instead of the `->` characters, you can also use space  , the equal sign `=` , and `--` as a delimiter between the start node and end node. With these alternative delimiters, the order of the nodes determines the arc direction.
    * `N1 N2=`<mark style="color:green;">`true`</mark> adds an arc from N1 to N1
    * `N1=N2=`<mark style="color:green;">`true`</mark> adds an arc from N1 to N2
    * `N1--N2=`<mark style="color:green;">`true`</mark> adds an arc from N1 to N2
    * `N1 N2=`<mark style="color:green;">`true`</mark> adds an arc from N1 to N2
* `Forbidden Arcs`
  * Specifies the addition or removal of Forbidden Arcs between nodes and classes
  * Syntax Examples:
    * `N1->N2` adds a Forbidden Arc from N1 to N2
    * `N1--N2` adds a Forbidden Arc between N1 and N2
    * `ClassA->ClassB` applies Forbidden Arcs from any nodes in ClassA to any nodes in ClassB
    * `N1`  `N2` removes any existing Forbidden Arc between N1 and N2. Note the <mark style="background-color:red;">space</mark> in the syntax, which triggers the removal of the Forbidden Arc.
* `Arc Comments`
  * Adds, updates, or removes **Arc Comments** to arcs in the active network. **Arc Comments** are stored in HTML format.
  * Syntax Examples:
    * `N1->N2=<p>This is a sample <b>Arc Comment</b>.</p>` adds an **Arc Comment** to the arc between N1 and N2.
    * `N1->N2=` removes an existing **Arc Comment** from the arc between N1 and N2.
    * The added **Arc Comment** can be edited in the **Arc Editor**: `Arc Contextual Menu > Edit`

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709431129/EditArcComment_kawyq0.png" alt="" width="563"><figcaption></figcaption></figure>

* `Arc Colors`
  * Defines colors for arcs in the active network. You can specify the color for each arc individually by providing the hex code of the color
  * Syntax Examples:
    * `N1->N2=000000` changes the color of the arc between N1 and N2 to black.
    * `N1->N2=FF0000` changes the color of the arc between N1 and N2 to bright red.
    * Note that there is no option to revert an arc color to the default color. When changing **Arc Colors** via a Dictionary, the colors must always be specified explicitly.
* `Structural Priors`
  * Assigns **Structural Priors** to arcs in the active network.
* `Fixed Arcs`
  * Applies **Fixed Arcs** to the active network or removes them.
  * Syntax Example:
    * `N1->N2=true` changes the arc between N1 and N2 to a **Fixed Arc**.
    * `N1->N2=false` changes the arc between N1 and N2 to a normal, non-fixed arc.
