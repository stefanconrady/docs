# 🤖 Bayesia Engine API

### Context&#x20;

* You can access many of BayesiaLab’s functions outside the graphical user interface by using a range of Bayesia Engine APIs.
* With the Bayesia Engine APIs, you can access BayesiaLab's functions programmatically andy integrate them into your own applications.
* You can license Bayesia Engine APIs for use in two main contexts, i.e., for software development and production deployment.

### For Software Development&#x20;

* Software developers can take advantage of a simple "developer" licensing model, which allows them to build applications that integrate the Bayesia Engine API into their own software projects.
* This flexible licensing option helps software developers experiment with all functions of the Bayesia Engine APIs without having to manage license fees that apply to Bayesia Engine APIs for production use.
* Naturally, the development phase is limited in time and precedes the production deployment.
* Note that programming skills in Java are required for successfully integrating the Java-based Bayesia Engine APIs into your software projects.

### For Production Deployment&#x20;

* The principal objective of using the Bayesia Engine API is to automate certain BayesiaLab functions and deploy them at scale.
* For a much-simplified approach to deploying the Bayesia Engine API, we now offer a RESTful API as a stateless Web Service.
* This allows you to perform inference with a given Bayesian network model using straightforward HTTPS calls. Hence, no coding in Java is required.
* A typical application would be real-time scoring of large volumes of streaming data.
* To scale up the processing capacity of the Bayesia Engine API in production, you can launch any number of instances of the API in parallel, subject only to the maxima specified in your license agreement.
* The license fee for a production license is based on the number of API instances that can run simultaneously, regardless of the physical computers involved and their locations. This means that one instance each on five different servers costs the same as five instances on a single server. Please note one instance means that a network model is loaded by the API, ready for an operation to be performed.
* If speed is of no concern, tasks can also be performed by sequentially loading and unloading different models, which would require only a single instance at any given time.

### API Overview&#x20;

* The following table summarizes the functions and limitations of the available configurations of the Bayesia Engine APIs.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690477618/Bayesia-Engine-API-Overview_zutqvm.svg" alt=""><figcaption></figcaption></figure>

</div>

### Bayesia Engine APIs

{% content-ref url="bayesia-engine-java-api-for-software-developers/" %}
[bayesia-engine-java-api-for-software-developers](bayesia-engine-java-api-for-software-developers/)
{% endcontent-ref %}

{% content-ref url="bayesia-engine-api-for-production-deployment/" %}
[bayesia-engine-api-for-production-deployment](bayesia-engine-api-for-production-deployment/)
{% endcontent-ref %}
