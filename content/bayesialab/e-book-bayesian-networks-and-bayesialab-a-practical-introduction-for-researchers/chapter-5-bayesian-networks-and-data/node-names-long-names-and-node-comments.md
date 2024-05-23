# Node Names, Long Names, and Node Comments

### Node Names, Long Names, and Node Comments&#x20;

The Node Names displayed by default are taken directly from the column header of the imported dataset. To keep the Graph Panel uncluttered, we will keep these "short" names as the formal Node Names. On the other hand, we may want to have longer, more descriptive names available when interpreting the network or presenting it to an audience.

BayesiaLab offers three levels of "node names" for each node:

* The Node Name uniquely identifies a node and is displayed by default.
* A Long Name can be displayed instead of the Node Name on the Graph Panel, on the Monitors in the Monitor Panel, on reports, and in the context of many analysis functions.
* A Node Comment provides additional space for supplemental information about a node. For instance, if nodes represent survey responses, the Node Comment could accommodate the verbatim survey question.

### Long Names &#x20;

Long Names can be added to a network in two ways:

* One by one for each node via the Properties tab of the Node Editor (`Node Context Menu > Edit > Properties`).
* Using a [Dictionary](../../user-guide/main-menu/data/associate-dictionary/) to provide Long Names for multiple nodes at once.

### Dictionary&#x20;

Given that we want to apply Long Names to 49 nodes, using a [Dictionary](../../user-guide/main-menu/data/associate-dictionary/) will be much more convenient. The format of a [Dictionary](../../user-guide/main-menu/data/export-dictionary.md) is rather straightforward:

* We define a plain text file that includes one Node Name per line. Spaces and special characters in the Node Name require backslash "\\" as an escape character.
* Each Node Name is followed by a delimiter (“=”, tab, or space) and then by the Long Name.

Here is a preview of the Dictionary:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/LongNameDictionary.png" alt=""><figcaption></figcaption></figure>

You can download the complete Dictionary file here:

![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/txt\_jjyarz.svg) [AmesLongNames.txt](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1689984072/AmesLongNames\_kqfwwg.txt)

To attach this Dictionary, select `Main Menu > Data > Associate Dictionary > Node > Long Names`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataAssociateDictionaryNodeLongeNames.png" alt=""><figcaption></figcaption></figure>

Next, we select the Dictionary file, “AmesLongNames.txt”.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataAssociateDictionaryNodeLongeNamesFileOpen.png" alt=""><figcaption></figcaption></figure>

Upon loading the Dictionary file, the appearance of the network does not change. Only if an error occurred would a warning triangle appear in the lower right corner of the Graph Window. Also, any error details would be available in the Console.

We now have the option of turning on the Long Names for individual nodes or all nodes. For our purposes, we want to see the Long Names on all nodes:

* Select all nodes, e.g., using Ctrl+A.
* `Node Context Monitor > Properties > Rendering Properties > Show Long Name`.
* Check the Show Long Name box in the pop-up window:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/RenderingPropertiesShowLongNamePopUp.png" alt=""><figcaption></figcaption></figure>

* Click OK.

Instead of the "short" Node Names, BayesiaLab now displays the Long Names for all nodes.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/LongNames.png" alt=""><figcaption></figcaption></figure>

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689958994/DataAssociateDictionaryNodeLongNames_pppfcs.mp4" %}
