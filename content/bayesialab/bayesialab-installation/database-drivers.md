# Database Drivers

### Context&#x20;

* If you plan to load data from a database or a data warehouse into BayesiaLab, you must first install the necessary database drivers.
* These drivers are typically provided by the respective database vendor.&#x20;
* The following example shows how to connect to a MySQL database running on localhost.

### Instructions&#x20;

* Select `Main Menu > Data > Open Data Source > Database`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982608.png" alt=""><figcaption></figcaption></figure>

* If no previous connection is defined, the **Data Import Wizard** will initially appear blank.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982610.png" alt=""><figcaption></figcaption></figure>

* Clicking  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982612.png) opens the list of currently installed drivers:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982614.png" alt=""><figcaption></figcaption></figure>

* If the required driver is listed as not available, and thus grayed out, you will need to download the driver from the database vendor. In our example, the appropriate driver for MySQL is **mm-mysql-2.0.7.jar**.
* For Mac OS X installations, we need to place **mm-mysql-2.0.7.jar** file into **/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home/lib/ext**
* In a Windows environment, we would put **mm-mysql-2.0.7.jar** into **C:\Program Files\Bayesia\BayesiaLab\jre1.6\lib\ext.** The specific file path on your system is obviously dependent on where you have installed BayesiaLab.&#x20;
* Once the driver file is put into place, please restart BayesiaLab and repeat steps 1 through 3.
* After clicking **Search Available Drivers**, the relevant driver will appear in the Driver List:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982616.png" alt=""><figcaption></figcaption></figure>

* Click **Select**, and you will proceed to the next step of the **Data Import Wizard**, which enables you to connect to your database using your credentials.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982618.png" alt=""><figcaption></figcaption></figure>

* Upon successful connection to the database server, the available database will appear under Catalog.
* Select the database, click **Apply,** and the drop-down menu of **Tables** will appear.
* Each table's fields can then be highlighted and selected to form a query. Upon selection, BayesiaLab will provide a data preview.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982620.png" alt=""><figcaption></figcaption></figure>

* Clicking opens up a larger window, which provides an opportunity to enter longer SQL statements.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982624.png" alt=""><figcaption></figcaption></figure>

* The elements in the lower portion of the dialogue box are identical to what is explained in the [Data Import Wizard](../user-guide/main-menu/data/open-data-source-data-import-wizard/) for text files in CSV format.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392725/2982626.png" alt=""><figcaption></figcaption></figure>

* Clicking Execute concludes the database-specific portion of the import process.&#x20;
