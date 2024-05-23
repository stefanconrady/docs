# Open Data Source (Data Import Wizard)

### Context <a href="#h2__1212884521_1381251416" id="h2__1212884521_1381251416"></a>

* The Data Import Wizard is the principal tool in BayesiaLab for preprocessing and importing external data.

### Data Sources <a href="#h2_1157195842_1381251416" id="h2_1157195842_1381251416"></a>

You can use BayesiaLab's Data Import Wizard to import data from two types of sources:

* Data tables in text format, in which data fields are separated by delimiters, such as comma, semicolon, tab, or pipe "|". The most common format is CSV.
* Data tables in SQL-compatible databases can be accessed via a JDBC driver. Third-party JDBC drivers are available for all major databases.

{% hint style="warning" %}
All data sources must be structured as a single table, i.e., with rows and columns. All table joins must be performed before importing the data in BayesiaLab.
{% endhint %}

### Usage <a href="#h2__1033115260_1381251416" id="h2__1033115260_1381251416"></a>

* To launch the **Data Import Wizard** for a data table in a&#x20;
  * text file, select `Main Menu > Data > Open Data Source > Text File`.
  * database, select `Main Menu > Data > Open Data Source > Database`.

Then, the **Data Import Wizard** guides you through five sequential steps. The first step of the **Data Import Wizard** depends on the data source, i.e., text file or database. All subsequent steps of the Data Import Wizard are the same for both types of data sources.

1. Data Structure Definition
   * [Data table in a text format](step-1-data-structure-definition-text-file.md)&#x20;
   * Data table in a database
2. Definition of Variable Types
3. Data Selection, Filtering, and Missing Value Processing&#x20;
4. Discretization and Aggregation
5. Import Report
