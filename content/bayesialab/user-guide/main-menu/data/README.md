# Data

﻿Data

#### **Open** Da**ta** S**ource** <a href="#data-opendatasource49003347" id="data-opendatasource49003347"></a>

This menu item allows opening the file or the database selector and then starts the **Data Import Wizard**.

* **Text** \*file:\* Once the file is read and the pre-processing done, a fully unconnected network is created in a new graph window, each attribute having one corresponding node. The set of Bayesian network **learning methods** becomes then available.
* **Database:** Once the database table is loaded and the pre-processing done, a fully unconnected network is created in a new graph window, each attribute having one corresponding node. The set of Bayesian network **learning methods** becomes then available.
* **Recent** **databases:** Keep a list of the recently opened databases. The **Data** **importation** **wizard** is directly opened on the selected file. The size of this list can be modified through the settings **Menus** .

#### **Associate** D**ata** S**ource** <a href="#data-associatedatasource49003347" id="data-associatedatasource49003347"></a>

&#x20;This menu item allows opening the **Data** **association** **wizard** in order to associate data from a text file or a database with an existing Bayesian network.

* **Recent** **databases:** Keep a list of the recently opened databases. The **Data** **association** **wizard** is directly opened on the selected file. The size of this list can be modified through the settings **Menus** .

When the network structure is modified during the association (addition of nodes or states), the conditional probability tables are automatically recomputed from the database. If the structure re- mains unmodified, the conditional probability tables are not modified.

#### **Associate** D**ictionary** <a href="#data-associatedictionary49003347" id="data-associatedictionary49003347"></a>

&#x20;This menu item allows defining the **properties** of the active Bayesian network thanks to text files. These properties concern arcs, nodes and states:

* Arc:
  * **Arcs:** allows associating a set of arcs to the network. The indicated arcs can be added or removed from the network. The arc removal will always be done before adding an arc. Before adding an arc, all the constraints belonging to the Bayesian network as well as the **arc** **constraints** and the **temporal indices** will be checked. If a constraint is not verified, then the arc won't be added.
  * **Forbidden Arcs:** allows associating with the network a set of **forbidden arcs** .
  * **Arc Comments:** allows associating with the network a set of **arc comments** .
  * **Arc Colors:** allows associating with the network a set of colors on the arcs.
  * **Fixed Arcs:** allows defining if some arcs are **fixed** or not.
* Node:
  * **Node** **Renaming:** allows renaming each node with a new name. These new names must be, of course, all different.
  * **Comments:** allows associating a **comment** with each node that is in the file.
  * **Classes:** allows organizing nodes in subsets called **classes** . A node can belong to several classes at the same time. These classes allow generalizing some **node's** **properties** to the nodes belonging to the same classes. They allow also creating constraints over the arc creation during learning.
  * **Colors:** allows associating colors with the nodes or **classes** that are in the file. The colors are written as Red Green Blue with 8 bits by channel in hexadecimal format (web format): for example the color red is 255 red 0 green 0 blue, it will give FF0000. Green gives 00FF00, yellow gives FFFF00, etc.
  * **Images:** allows associating colors with the nodes or **classes** that are in the file. The images are represented by their path relatively to the directory where the dictionary is.
  * **Costs:** allows associating with each node a **cost** . A node without cost is called not observable.
  * **Temporal** **Indices:** allows associating **temporal** **indices** with the nodes that are in the file. These temporal indexes are used by the BayesiaLab's learning algorithms to take into account any constraints over the probabilistic relations, as for example the no adding arcs between future nodes to past nodes. The rule that is used to add an arc from node N1 to node N2 is:&#x20;
  * If the temporal index of N1 is positive or null, then the arc from N1 to N2 is only possible if the temporal index of N2 is greater of equal to the index of N1.&#x20;
  * **Local** **Structural** **Coefficients:** allows setting the **local** **structural** **coefficient** of each specified node or each node of each specified class.&#x20;
  * **State** **Virtual** **Numbers:** allows setting the **state** **virtual** **number** of each specified node or each node of each specified class.&#x20;
  * **Locations:** allows setting the position of each node.&#x20;
* State:
  * **State Renaming:** allows renaming each state of each node with a new name.
  * **State** **Values:** allows associating with each state of each node a **numerical value** .
  * **State** **Long** **Names:** allows associating with each state of each node a **long** **name** more explicit than the default state name. This name can be used in the different ways to export a database, in the html reports and in the monitors.
  * **Filtered States:** allows defining a state to each node as a **filtered state** .

<table><thead><tr><th>Dictionary File Structures</th><th width="142.33333333333331"></th><th></th></tr></thead><tbody><tr><td>Arc</td><td>Arcs</td><td>Name of the arc's starting node or class, <strong>-></strong> , <strong>&#x3C;-</strong> or even <strong>--</strong> to indicate the both possible orientations, name of the arc's ending node or class, <em>Equal, Space</em> or <em>Tab</em> , <strong>true</strong> for an added arc or <strong>false</strong> for a removed arc. The last occurrence is always chosen.</td></tr><tr><td>Forbidden Arcs</td><td>Name of the arc's starting node or class, <strong>-></strong> , <strong>&#x3C;-</strong> or even <strong>--</strong> to indicate the both possible orientations, name of the arc's ending node or class.</td><td></td></tr><tr><td>Comments</td><td>Name of the arc's starting node or class, <strong>-></strong> , <strong>&#x3C;-</strong> or even <strong>--</strong> to indicate the both possible orientations, name of the arc's ending node or class, <em>Equal, Space</em> or <em>Tab</em> , <strong>comment</strong> . The <strong>comment</strong> can be any character string without return (in html or not). The last occurrence is always chosen.</td><td></td></tr><tr><td>Colors</td><td>Name of the arc's starting node or class, <strong>-></strong> , <strong>&#x3C;-</strong> or even <strong>--</strong> to indicate the both possible orientations, name of the arc's ending node or class, <em>Equal, Space</em> or <em>Tab</em> , <strong>color</strong> . The <strong>color</strong> is defined as Red Green Blue 8 bits by channel color written in hexadecimal (web format). For example green gives 00FF00, yellow gives FFFF00, blue gives 0000FF, pink gives FFC0FF,etc. The last occurrence is always chosen.</td><td></td></tr><tr><td>Fixed Arcs</td><td>Name of the arc's starting node or class, <strong>-></strong> , <strong>&#x3C;-</strong> or even <strong>--</strong> to indicate the both possible orientations, name of the arc's ending node or class, <em>Equal, Space</em> or <em>Tab</em> , <strong>true</strong> for an fixed arc or <strong>false</strong> for a not fixed arc. The last occurrence is always chosen.</td><td></td></tr><tr><td>Node</td><td>Node Renaming</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> new node name.<br>The <strong>new name</strong> must be valid (different from t or T and without?).<br>A node can be present only once otherwise the last occurrence is chosen.</td></tr><tr><td>Comments</td><td>Name of the node or the class <em>Equal, Space</em> or <em>Tab</em> Comment.<br>The <strong>comment</strong> can be any character string without return (in html or not).<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Classes</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> Name of the class.<br>The <strong>class</strong> can be any character string.<br>A node present several times will be associated with different classes.</td><td></td></tr><tr><td>Colors</td><td>Name of a node or a class <em>Equal, Space</em> or <em>Tab</em> Color<br>The <strong>color</strong> is defined as Red Green Blue 8 bits by channel color written in hexadecimal (web format). For example green gives 00FF00, yellow gives FFFF00, blue gives 0000FF, pink gives FFC0FF, etc.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Images</td><td>Name of a node or a class <em>Equal, Space</em> or <em>Tab</em> path to the image relatively to the directory where the dictionary is.<br>The <strong>image path</strong> must be a valid relative path or an empty string.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Costs</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> value of the cost or empty if we want the node to be not observable.<br>The <strong>cost</strong> is an empty string or a real number superior or equal to 1.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Temporal Indices</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> value of the index or empty if we want to delete an already existent index<br>The <strong>index</strong> is an integer.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Local Structural Coefficients</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> value of the local structural coefficient or empty if we want to reset to the default value 1.<br>The <strong>local structural coefficient</strong> is an empty string or a real number superior to 0.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>State Virtual Numbers</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> virtual number of states or empty if we want to delete an already existent number.<br>The <strong>state virtual number</strong> is an empty string or an integer superior or equal to 2.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Locations</td><td>Name of the node <em>Equal, Space</em> or <em>Tab</em> , position.<br>The <strong>location</strong> is represented by two real numbers separated by a <em>Space</em> . The first number represent the x-coordinate of the node and the second number the y-coordinate.<br>A node can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>State</td><td>State Renaming</td><td>Name of the node or class <em>dot (.)</em> name of the state <em>Equal, Space</em> or <em>Tab</em> new state name or<br>State <em>name Equal, Space</em> or <em>Tab</em> new state name if we want to rename the state for all nodes.<br>The <strong>new name</strong> is a valid state name.<br>A state can be present only once otherwise the last occurrence is chosen.</td></tr><tr><td>State Values</td><td>Name of the node or class <em>dot (.)</em> name of the state <em>Space</em> or <em>Tab</em> real value or<br>Name of the state <em>Equal, Space</em> or <em>Tab</em> real value if we want to associate a value with a state whatever the node.<br>The <strong>value</strong> is a real number.<br>A state can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>State Long Names</td><td>Name of the node or class <em>dot (.)</em> name of the state <em>Equal, Space</em> or <em>Tab</em> long name or<br>Name of the state <em>Equal, Space</em> or <em>Tab</em> long name if we want to associate a long name with a state whatever the node.<br>The <strong>long name</strong> is a string.<br>A state can be present only once otherwise the last occurrence is chosen.</td><td></td></tr><tr><td>Filtered States</td><td>Name of the node or class <em>dot (.)</em> name of the filtered state.<br>Name of the filtered state if we want to set the filter property to the state whatever the node.<br>A state can be present only once otherwise the last occurrence is chosen.</td><td></td></tr></tbody></table>

As indicated by the syntax, the name of the node, class or state in the text file cannot contain equal, space or tab characters. If the node names contain such characters in the networks, those characters must be written with a {color} (backslash) character before in the text file: for example the node named Visit Asia will be written Visit\ Asia in the file.

In order to specifically differenciate a nam which is the same for a classe, a node or a state, you must add at the end of the name the suffix "c" for a class, "n" for a node and "s" for a state.

If your network contains not-ASCII characters, you must save your own dictionaries with UTF-8 (Unicode) encoding. For example, in MS Excel, choose "save as" and select "Text Unicode (\*.txt)" as type of file. In Notepad, choose "save as" and select "UTF-8" as encod- ing. If your file contains only ASCII character you can let the default encoding (depending on the platform) but it is strongly encouraged to use UTF-8 (Unicode) encoding in order to create dictionary files that doesn't depend on the user's platform. So, for example, a chinese dictionary can be read by a german without any problem whatever the used platforms are. If you are not sure how to save a file with UTF-8 encoding, you should export a dictionary with BayesiaLab, modify and save it (with any text editor) and load it in BayesiaLab.

#### &#x20;**Export Dictionary** <a href="#data-exportdictionary49003347" id="data-exportdictionary49003347"></a>

&#x20;This menu item allows exporting the different kinds of dictionaries in text files.

The dictionary files are saved with UTF-8 (Unicode) encoding in order to support any character of any language. An option, in the Import and Associate preferences: **Save** **Format** , allows saving or not the BOM (Byte Order Mask) at the beginning of the file. The BOM increases the compatibility with Microsoft applications. On other platform like Unix, Linux or Mac OS X, the BOM is not necessary and, in come cases, is considered as simple extra characters at the beginning of the file.

#### **Associate** **an** E**vidence** S**cenario File** <a href="#data-associateanevidencescenariofile49003347" id="data-associateanevidencescenariofile49003347"></a>

This menu item allows associating an **evidence** **scenario** **file** with the network.&#x20;

#### **Export** **an** E**vidence** S**cenario File** <a href="#data-exportanevidencescenariofile49003347" id="data-exportanevidencescenariofile49003347"></a>

This menu item allows exporting into a text file an **evidence** **scenario file** associated with the network.

#### &#x20;<a href="#data-generatedata49003347" id="data-generatedata49003347"></a>

#### **Save** D**ata** <a href="#data-savedata49003347" id="data-savedata49003347"></a>

This menu item allows saving the base associated with the network including the results of the various pre-processing that have been carried out within the **data** **importation** **wizard** (discretization, aggregation, filtering,). If the imported database still contains missing values and if the **selected** **algorithm** to process the missing values is one of the two imputation algorithms (static or dynamic), then option will allow you to realize all your imputation tasks by saving a database without any missing values. Indeed, each missing value is replaced by taking into account its conditional probability distri- bution, returned by the Bayesian network, given all the known values of the line. If the database contains **data** **for** **test** **and** **data** **for** **learning,** the user can choose which kind of data he wants to save: only learning data, only test data or the whole data. It is also possible to save only the data corresponding to the selected nodes.

\
The states' long name can be saved instead of the states' name. The numerical values in the database associated with the continuous nodes can be saved if they exist. If there is no numerical values asso- ciated with the database and if the option is checked, the numerical values will be created by randomly generating a value in each concerned interval. If the database contains weights, they will be saved as the first column in the output file.&#x20;

#### **Imputation** <a href="#data-imputation49003347" id="data-imputation49003347"></a>

&#x20;Allows the imputation of the missing values of the associated database according to the mode selected in the following dialog box:

\
The data will be saved in the specified file and the long name of the states will be used as specified. If the database contains **data** **for** **test** **and** **data** **for** **learning,** the user can choose on which kind of data he wants to perform imputation: only learning data, only test data or the whole data. The states' long name can be saved instead of the states' name. The numerical values in the database associated with the continuous nodes can be saved if they exist. If there is no numerical values associated with the database and if the option is checked, the numerical values will be created by randomly generating a value in each concerned interval. However, if there are numerical values in the database, the missing numerical values will be generated from the distribution function of each interval. If the database contains weights, they will be saved as the first column in the output file.&#x20;

#### **Graphs** <a href="#data-graphs49003347" id="data-graphs49003347"></a>

Opens the **graph editor** if a database is associated with the current network.

***

***

***
