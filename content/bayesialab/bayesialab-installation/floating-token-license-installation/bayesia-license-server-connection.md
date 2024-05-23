# Bayesia License Server Connection

{% hint style="warning" %}
* Unlike a [BayesiaLab Single-User/Single-Machine License](../single-user-single-machine-license-installation/), a BayesiaLab Floating Token License **requires a continuous connection** to bls1.bayesia.com:2424 while using the BayesiaLab software.
* Note that this connection only transmits software credentials for validation purposes.
* The BayesiaLab software always runs locally on your hardware, and no data or models are transmitted to the Bayesia License Server.
{% endhint %}

### Starting BayesiaLab

* Each time you start BayesiaLab, you will be prompted to enter your **User Name** and **Password**.
* Check "Remember Password" to save your credentials.
* This connects your BayesiaLab software to the [Bayesia License Server](../../bayesia-license-server-bls/) to validate your credentials.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691800067/BL-Splash-Screen-Login_x7760u.png" alt="" width="375"><figcaption></figcaption></figure>

* Upon connecting successfully, BayesiaLab will start up.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691800334/BL-Splash-Screen_edum36.png" alt="" width="375"><figcaption></figcaption></figure>

### Troubleshooting the Connection

* Please open a web browser, go to [http://bls1.bayesia.com](http://bls1.bayesia.com), and see whether you can access the [Bayesia License Server](../../bayesia-license-server-bls/) Login Page shown below.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691797505/pika-1691797288706-1x_ivzbla.png" alt=""><figcaption></figcaption></figure>

* If you can access the [Bayesia License Server](../../bayesia-license-server-bls/) Login Page but do not get a response upon entering your credentials, it means that BayesiaLab could not connect with the [Bayesia License Server](../../bayesia-license-server-bls/), and you most likely have a problem with your firewall.
* Please ask your IT administrator to define an outbound rule that will allow BayesiaLab to communicate with the Bayesia License Server at bls1.bayesia.com:2424.
* For instance, if you had BayesiaLab installed in the _C:\Program Files\Bayesia_ directory, your IT administrator would need to establish an outbound rule for _C:\Program Files\Bayesia\BayesiaLab\jreXXX\bin\javaw.exe._

### Workaround

* If you cannot solve the firewall issue, a workaround is to use an external, non-corporate Internet connection, e.g., at home or using a cellphone as a hotspot, etc., and connect to the BayesiaLab License Server from there without the firewall blocking problem. Then, you can enable the “Borrow Session” option on the second screen when you start up BayesiaLab. Then, you can work offline for the time you have specified.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691800220/BL-Borrow-Session_hfbnav.png" alt="" width="375"><figcaption></figcaption></figure>
