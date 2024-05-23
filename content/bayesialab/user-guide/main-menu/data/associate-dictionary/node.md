# Node

### Node

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709412076/Associate-Dictionary-Node_c8v76s.png" alt="" width="375"><figcaption></figcaption></figure>

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
