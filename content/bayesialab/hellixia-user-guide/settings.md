# Settings

### Context

* To utilize the Hellixia functions, BayesiaLab must connect to the OpenAI or Mistral APIs using a personal API Key.

{% hint style="warning" %}
* OpenAI and Mistral are third-party services that can be accessed through BayesiaLab; however, it is not part of the BayesiaLab software. As a result, Bayesia makes no representations.&#x20;
* A subscription fee payable to OpenAI or Mistral may be required to obtain your personal API Key.
{% endhint %}

### OpenAI

* Obtain your personal API key from the OpenAI website.

<table data-card-size="large" data-view="cards" data-full-width="false"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td><strong>OpenAI</strong></td><td></td><td></td><td><a href="https://openai.com/">https://openai.com/</a></td><td><a href="../../.gitbook/assets/OpenAI-API-Keys.png">OpenAI-API-Keys.png</a></td></tr></tbody></table>

* Once you have obtained your API Key, enter it into your locally-installed BayesiaLab software under `Main Menu > Windows > Preferences > Tools > Hellixia`

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690041192/OpenAISettings_bsghbz.png" alt=""><figcaption></figcaption></figure>

### Endpoints

If you want to utilize an alternative to OpenAI and Mistral, you can deploy models in your own Microsoft Azure account for example. The process involves creating endpoints.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690041057/EndPoints_hdhruv.png" alt=""><figcaption></figcaption></figure>

The URL is structured as follows: `https://{your-resource-name}.openai.azure.com/openai/deployments/{deployment-id}/chat/completions?api-version={api-version}`."

In this URL:

* `{your-resource-name}` should be replaced with the name of your Azure OpenAI resource.
* `{deployment-id}` should be replaced with the ID of the specific deployment.
* `{api-version}` should be replaced with the version of the API you're using. This follows the YYYY-MM-DD format.

For further information, visit Microsoft's official documentation at [`https://learn.microsoft.com/en-us/azure/cognitive-services/openai/reference`](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/reference)

### SSL Proxy

If you're operating behind a proxy that enforces SSL rewriting or redirection, you might encounter the following error message:&#x20;

`'PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target.'`&#x20;

If you encounter this issue, it will be necessary to point BayesiaLab towards the truststore, where the approved certificates are kept.&#x20;

#### Workflow

* Go to `Main Menu > Windows > Preferences > General.`
* Click on the folder icon to locate and select the **BayesiaLab.cfg** file.
* Navigate to the end of the file, where you'll locate the \[JavaOptions] section.
  *   If you're using Windows, you should add the following two lines:

      `java-options=-Djavax.net.ssl.trustStoreType=Windows-ROOT` \
      `java-options=-Djavax.net.ssl.trustStore=NUL`
  *   For MacOSX users, instead, add:

      `java-options=-Djavax.net.ssl.trustStoreType=KeychainStore` \
      `java-options=-Djavax.net.ssl.trustStore=/dev/null`
* After these changes, save the file and then restart BayesiaLab for the updates to take effect.

