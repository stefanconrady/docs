# Chapter 4: Knowledge Modeling & Probabilistic Reasoning

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

This chapter presents a workflow for encoding expert knowledge and subsequently performing omnidirectional probabilistic inference in the context of a real-world reasoning problem. While Chapter 1 provided a general motivation for using Bayesian networks as an analytics framework, this chapter highlights the perhaps unexpected relevance of Bayesian networks for reasoning in everyday life. The example proves that “common-sense” reasoning can be rather tricky. On the other hand, encoding “common-sense knowledge” in a Bayesian network turns out to be uncomplicated. We want to demonstrate that reasoning with Bayesian networks can be as straightforward as doing arithmetic with a spreadsheet.

### Background & Motivation&#x20;

#### Complexity & Cognitive Challenges&#x20;

It is presumably fair to state that reasoning in complex environments creates cognitive challenges for humans. Adding uncertainty to our observations of the problem domain, or even considering the uncertainty regarding the structure of the domain itself, makes matters worse. When uncertainty blurs so many premises, it can be particularly difficult to find a common reasoning framework for a group of stakeholders.

#### No Data, No Analytics.&#x20;

If we had hard observations from our domain in the form of data, it would be quite natural to build a traditional analytic model for decision support. However, the real world often yields only fragmented data or no data at all. It is not uncommon that we merely have the opinions of individuals who are more or less familiar with the problem domain.

#### To an Analyst With Excel, Every Problem Looks Like Arithmetic.&#x20;

In the business world, spreadsheets are typically used to model the relationships between variables in a problem domain. Also, in the absence of hard observations, it is reasonable that experts provide assumptions instead of data. Any such expert knowledge is typically encoded as single-point estimates and formulas. However, using single values and formulas instantly oversimplifies the problem domain: firstly, the variables, and the relationships between them, become deterministic; secondly, the left-hand side versus right-hand side nature of formulas restricts inference to only one direction.

#### Taking No Chances!&#x20;

Since spreadsheets' cells and formulas are deterministic and only work with single-point values, they are well suited for encoding “hard” logic but not at all for “soft” probabilistic knowledge that includes uncertainty. As a result, any uncertainty has to be addressed with workarounds, often in the form of trying out multiple scenarios or by working with simulation add-ons.

#### It Is a One-Way Street!&#x20;

The lack of omnidirectional inference, however, may be the bigger issue in spreadsheets. As soon as we create a formula linking two cells in a spreadsheet, e.g., B1=function(A1), we preclude any evaluation in the opposite direction, from B1 to A1.

Assuming that A1 is the cause and B1 is the effect, we can indeed use a spreadsheet for inference in the causal direction, i.e., perform a simulation. However, even if we were certain about the causal direction between them, unidirectionality would remain a concern. For instance, if we were only able to observe the effect B1, we could not infer the cause A1, i.e., we could not perform a diagnosis from effect to cause. The one-way nature of spreadsheet computations prevents this.

#### Bayesian Networks to the Rescue!&#x20;

Bayesian networks are probabilistic by default and handle uncertainty “natively.” A Bayesian network model can work directly with probabilistic inputs and probabilistic relationships and deliver correctly computed probabilistic outputs. Also, whereas traditional models and spreadsheets are of the form y=f(x), Bayesian networks do not have to distinguish between independent and dependent variables. Rather, a Bayesian network represents the entire joint probability distribution of the system under study. This representation facilitates omnidirectional inference, which we typically require for reasoning about a complex problem domain, such as the example in this chapter.

### Example: Where is My Bag?&#x20;

While most other examples in this book resemble proper research topics, we present a rather casual narrative to introduce probabilistic reasoning with Bayesian networks. It is a common situation taken straight from daily life, for which a “common-sense interpretation” may appear more natural than our proposed formal approach. As we shall see, dealing formally with informal knowledge provides a robust basis for reasoning under uncertainty.

#### Did My Checked Luggage Make the Connection?&#x20;

Most travelers will be familiar with the following hypothetical situation or something fairly similar: You are traveling from Singapore to Los Angeles and need to make a flight connection in Tokyo. Your first flight segment from Singapore to Tokyo is significantly delayed, and you arrive in Tokyo with barely enough time to make the connection. You have to run from Terminal 1, where you just landed, to Terminal 2, where your flight to Los Angeles will depart. The boarding process is already underway by the time you get to the departure gate for Los Angeles.\


<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689985050/SIN_NRT_LAX_dbbyni.svg" alt=""><figcaption></figcaption></figure>

</div>

#### Problem #1&#x20;

Out of breath, you check in with the gate agent, who informs you that the luggage you checked in at Singapore may or may not make the connection. She apologetically states there is only a 50/50 chance you will get your bag upon arrival at your destination airport, Los Angeles.

Once you have landed in Los Angeles, you head straight to the baggage claim and wait for the first pieces of luggage to appear on the baggage carousel. Bags come down the chute onto the carousel at a steady rate. After five minutes of watching fellow travelers retrieve their luggage, you wonder what the chances are that you will ultimately get your bag. You reason that if the bag had indeed made it onto the plane, it would be increasingly likely to appear among the remaining pieces to be unloaded. However, you do not know for sure that your piece was actually on the plane. Then, you think, you better get in line to file a claim at the baggage office. Is that reasonable? How should you update your expectations about getting your bag as you wait?

#### Problem #2&#x20;

As you contemplate your next move, you see a colleague picking up his suitcase. As it turns out, your colleague was traveling on the very same itinerary as you, i.e., Singapore – Tokyo – Los Angeles. His luggage made it, so you conclude that you better wait at the carousel for the very last piece to be delivered. How does the observation of your colleague’s suitcase change your belief in the arrival of your bag? Does all that even matter? After all, the bag either made the connection or not. The fact that you now observe something after the fact cannot influence what happened earlier, right?

### Knowledge Modeling for Problem #1&#x20;

This problem domain can be explained by a causal Bayesian network, only using a few common-sense assumptions. We demonstrate how to combine different pieces of available —but uncertain—knowledge into a network model. Our objective is to calculate the correct degree of belief in the arrival of your luggage as a function of time and your own observations.

Per our narrative, we obtain the first piece of information from the gate agent in Tokyo who manages the departure to Los Angeles. She says there is a 50/50 chance that your bag is on the plane. More formally, we express this as:

�(��������������=����)=0.5\


We encode this probabilistic knowledge in a Bayesian network by creating a node. In BayesiaLab, we click the Node Creation Mode icon () and then point to the desired position on the Graph Panel.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_14-33-241.jpg)

Once the node is in place, we update its name to “Your Bag on Plane” by double-clicking the default name N1. Then, by double-clicking the node itself, we open BayesiaLab’s Node Editor. Under the tab Probability Distribution > Probabilistic, we define the probability that Your Bag on Plane=True, which is 50%, as per the gate agent’s statement. Given that these probabilities do not depend on any other variables, we speak of marginal probabilities. Note that in BayesiaLab, probabilities are always expressed as percentages:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-15-271.jpg)

Assuming there is no other opportunity for losing luggage within the destination airport, your chance of ultimately receiving your bag should be identical to the probability of your bag being on the plane, i.e., on the flight segment to your final destination airport. More simply, if it is on the plane, then you will get it:

�(�����������������=����|��������������=����)=1�(�����������������=�����|��������������=����)=0\


Conversely, the following must hold too:

�(�����������������=�����|��������������=�����)=1�(�����������������=����|��������������=�����)=0\


We now encode this knowledge into our network. We add a second node, Your Bag on Carousel, and then click the Arc Creation Mode icon . Next, we click and hold the cursor on Your Bag on Plane, drag the cursor to Your Bag on Carousel, and finally release. This produces a simple, manually specified Bayesian network:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_15-35-471.jpg)

The yellow warning triangle  indicates that probabilities need to be defined for the node Your Bag on Carousel. Unlike the previous instance, where we only had to enter marginal probabilities, we now need to define the probabilities of the states of the node Your Bag on Carousel conditional on the states of Your Bag on Plane. In other words, we need to fill the Conditional Probability Table to quantify this parent-child relationship. We open the Node Editor and enter the values from the equations above.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/Node\_Editor1.jpg)

#### Introduction of Time&#x20;

Now we add another piece of contextual information that has not been mentioned yet in our story. From the baggage handler who monitors the carousel, you learn that 100 pieces of luggage in total were on your final flight segment, from the hub to the destination. After you wait for one minute, 10 bags have appeared on the carousel, and they keep coming out at a very steady rate. However, yours is not among the first ten that were delivered in the first minute. At the current rate, it would now take 9 more minutes for all bags to be delivered to the baggage carousel.

Given that your bag was not delivered in the first minute, what is your new expectation of ultimately getting your bag? How about after the second minute of waiting? Quite obviously, we need to introduce a time variable into our network. We create a new node Time and define discrete time intervals \[0,...,10] to serve as its states.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-00-321.jpg)

By default, all new nodes initially have two states, True and False. We can see this by opening the Node Editor and selecting the States tab:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-17-251.jpg)

By clicking on the Generate States button, we create the states we need for our purposes. Here, we define 11 states, starting at 0 and increasing by 1 step:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-18-421.jpg)

The Node Editor now shows the newly-generated states:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-20-081.jpg)

Beyond defining the states of Time, we also need to define their marginal probability distribution. For this, we select the tab Probability Distribution > Probabilistic. Naturally, no time interval is more probable than another one, so we should apply a uniform distribution across all states of Time. BayesiaLab provides a convenient shortcut for this purpose. Clicking the Normalize button places a uniform distribution across all cells, i.e., 9.091% per cell.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-22-511.jpg)

Once Time is defined, we draw an arc from Time to Your Bag on Carousel. By doing so, we introduce a causal relationship, stating that Time influences the status of your bag.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-08-511.jpg)

The warning triangle  once again indicates that we need to define further probabilities concerning Your Bag on Carousel. We open the Node Editor to enter these probabilities into the Conditional Probability Table:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-10-521.jpg)

Note that the probabilities of the states True and False now depend on two-parent nodes. For the upper half of the table, it is still quite simple to establish the probabilities. If the bag is not on the plane, it will not appear on the baggage carousel under any circumstance, regardless of Time. Hence, we set False to 100 (%) for all rows in which Your Bag on Plane=False.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-27-501.jpg)

However, given that Your Bag on Plane=True, the probability of seeing it on the carousel depends on the time elapsed. Now, what is the probability of seeing your bag at each time step? Assuming that all luggage is shuffled extensively through the loading and unloading processes, there is a uniform probability distribution that the bag is anywhere in the pile of luggage to be delivered to the carousel. As a result, there is a 10% chance that your bag is delivered in the first minute, i.e. within the first batch of 10 out of 100 luggage pieces. Over a period of two minutes, there is a 20% probability that the bag arrives, and so on. Only when the last batch of 10 bags remains undelivered, we can be certain that your bag is in the final batch, i.e. there is a 100% probability of the state True in the tenth minute. We can now fill out the Conditional Probability Table in the Node Editor with these values. Note that we only need to enter the values in the True column and then highlight the remaining empty cells. Clicking Complete prompts BayesiaLab to automatically fill in the False column to achieve a row sum of 100%:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-30-091.jpg)

Now we have a fully specified Bayesian network, which we can evaluate immediately.

### Evidential Reasoning for Problem #1&#x20;

BayesiaLab’s Validation Mode provides the tools for using the Bayesian network we built for omnidirectional inference. We switch to the Validation Mode via the corresponding icon , in the lower left-hand corner of the main window, or via the keyboard shortcut F5:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-12\_20-55-421.png)

Upon switching to this mode, we double-click on all three nodes to bring up their associated Monitors, which show the nodes’ current marginal probability distributions. We find these Monitors inside the Monitor Panel on the right-hand side of the main window:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-33-471.jpg)

#### Inference Tasks&#x20;

If we filled the Conditional Probability Table correctly, we should now be able to validate at least the trivial cases straight away, e.g. for Your Bag on Plane=False.

Inference from Cause to Effect: Your Bag on Plane=False

We perform inference by setting such evidence via the corresponding Monitor in the Monitor Panel. We double-click the bar that represents the State False:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/11.jpg)

The setting of the evidence turns the node and the corresponding bar in the Monitor green:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic_Reasoning-web-resources/image/2015-07-16_16-35-11.jpg" alt=""><figcaption></figcaption></figure>

The Monitor for Your Bag on Carousel shows the result. The small gray arrows overlaid on top of the horizontal bars furthermore indicate how the probabilities have changed by setting this most recent piece of evidence:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/21.jpg)

Indeed, your bag could not possibly be on the carousel because it was not on the plane in the first place. The inference we performed here is indeed trivial, but it is reassuring to see that the Bayesian network properly “plays back” the knowledge we entered earlier.

Omnidirectional Inference: Your Bag on Carousel=False, Time=1

The next question, however, typically goes beyond our intuitive reasoning capabilities. We wish to infer the probability that your bag made it onto the plane, given that we are now in minute 1, and the bag has not yet appeared on the carousel. This inference is tricky because we now have to reason along multiple paths in our network.

#### Diagnostic Reasoning&#x20;

The first path is from Your Bag on Carousel to Your Bag on Plane. This type of reasoning from effect to cause is more commonly known as diagnosis. More formally, we can write:

�(��������������=����|�����������������=�����)\


#### Inter-Causal Reasoning&#x20;

The second reasoning path is from Time via Your Bag on Carousel to Your Bag on Plane. Once we condition on Your Bag on Carousel, i.e. by observing the value, we open this path, and information can flow from one cause, Time, via the common effect, Your Bag on Carousel, to the other cause, Your Bag on Plane. Hence, we speak of “inter-causal reasoning” in this context. The specific computation task is:

�(��������������=����|�����������������=�����,����=1)\


#### Bayesian Networks as Inference Engine&#x20;

How do we go about computing this probability? We do not attempt to perform this computation ourselves. Rather, we rely on the Bayesian network we built and BayesiaLab’s exact inference algorithms. However, before we can perform this inference computation, we need to remove the previous piece of evidence, i.e. Your Bag on Plane=True. We do this by right-clicking the relevant node and then selecting Remove Evidence from the Contextual Menu. Alternatively, we can remove all evidence by clicking the Remove All Observations icon .

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-36-471.jpg)

Then, we set the new observations via the Monitors in the Monitor Panel. The inference computation then happens automatically.&#x20;

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-42-531.jpg)

Given that you do not see your bag in the first minute, the probability that your bag made it onto the plane is now no longer at the marginal level of 50% but is reduced to 47.37%.

#### Inference as a Function of Time&#x20;

Continuing with this example, how about if the bag has not shown up in the second minute, in the third minute, etc.? We can use one of BayesiaLab’s built-in visualization functions to analyze this automatically. To prepare the network for this type of analysis, we first need to set a Target Node, which, in our case, is Your Bag on Plane. Upon right-clicking this node, we select Set as Target Node. Alternatively, we can double-click the node, or one of its states in the corresponding Monitor, while holding T.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-44-251.jpg)

Upon setting the Target Node, Your Bag on Plane is marked with a bullseye symbol. Also, the corresponding Monitor is now highlighted in red. Before we continue, however, we need to remove the evidence from the Time Monitor. We do so by right-clicking the Monitor and selecting Remove Evidence from the Contextual Menu.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-46-521.jpg)

Then, we select Analysis > Visual > Influence Analysis on Target Node.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-08-06\_17-07-531.jpg)

The resulting graph shows the probabilities of receiving your bag as a function of the discrete time steps. To see the progression of the True state, we select the corresponding tab at the top of the window.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-08-06\_17-53-511.jpg)

### Knowledge Modeling for Problem #2&#x20;

Continuing with our narrative, you now notice a colleague of yours in the baggage claim area. As it turns out, your colleague was traveling on the same itinerary as you, i.e., Singapore – Tokyo – Los Angeles, so he had to make the same tight connection. Unlike you, he has already retrieved his bag from the carousel. You assume that his luggage being on the airplane is not independent of your luggage being on the same plane, so you take this as a positive sign. How do we formally integrate this assumption into our existing network?

To encode any new knowledge, we first need to switch back to the Modeling Mode (F4). Then, we duplicate the existing nodes Your Bag on Plane and Your Bag on Carousel by copying and pasting them into the same Graph Panel using the common shortcuts, Ctrl+C and Ctrl+V.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-56-561.jpg)

In the copy process, BayesiaLab prompts us for a Copy Format, which would only be relevant if we intended to paste the selected portion of the network into another application, such as PowerPoint. As we paste the copied nodes into the same Graph Panel, the format does not matter.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_16-58-181.jpg)

Upon pasting, by default, the new nodes have the same names as the original ones plus the suffix “\[1]”.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-03-471.jpg)

Next, we reposition the nodes on the Graph Panel and rename them to show that the new nodes relate to your colleague’s situation, rather than yours. To rename the nodes we double-click the Node Names and overwrite the existing label.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-07-061.jpg)

The next assumption is that your colleague’s bag is subject to exactly the same forces as your luggage. More specifically, the successful transfer of your and his luggage is a function of how many bags could be processed in Tokyo given the limited transfer time. To model this, we introduce a new node and name it Transit.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-08-411.jpg)

We create 7 states of ten-minute intervals for this node, which reflect the amount of time available for the transfer, i.e., from 0 to 60 minutes.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-37-281.jpg)

\


![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-15\_17-38-461.jpg)

Furthermore, we set the probability distribution for Transit. For expository simplicity, we apply a uniform distribution using the Normalize button.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-06-11\_13-14-321.jpg)

Now that the Transit node is defined, we can draw the arcs connecting it to Your Bag on Plane and Colleague’s Bag on Plane.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-39-271.jpg)

The yellow warning triangles  indicate that the [Conditional Probability Tables](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/conditional-probability-tables-2392452) of Your Bag on Plane and Colleague’s Bag on Plane have yet to be filled. Thus, we need to open the [Node Editor](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor) and set these probabilities. We will assume that the probability of your bag making the connection is 0% given a Transit time of 0 minutes and 100% with a Transit time of 60 minutes. Between those values, the probability of a successful transfer increases linearly with time.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-06-11\_13-36-131.jpg)

The very same function also applies to your colleague’s bag, so we enter the same conditional probabilities for the node Colleague’s Bag on Plane by copying and pasting the previously entered table.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-41-541.jpg)

### Evidential Reasoning for Problem #2&#x20;

Now that the probabilities are defined, we switch to the [Validation Mode](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/view-validation-mode) (F5); our updated Bayesian network is ready for inference again.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-50-521.jpg)

We simulate a new scenario to test this new network. For instance, we move to the fifth minute and set evidence that your bag has not yet arrived.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-51-461.jpg)

Given these observations, the probability of Your Bag on Plane=True is now 33.33%. Interestingly, the probability of Colleague’s Bag on Plane has also changed. As evidence propagates omnidirectionally through the network, our two observed nodes do indeed influence Colleague’s Bag on Plane. A further iteration of the scenario in our story is that we observe Colleague’s Bag on Carousel=True, also in the fifth minute.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-07-16\_17-52-411.jpg)

Given the observation of Colleague’s Bag on Carousel, even though we have not yet seen Your Bag on Carousel, the probability of Your Bag on Plane increases to 56.52%. Indeed, this observation should change your expectation quite a bit. The small gray arrows on the blue bars inside the Monitor for Your Bag on Plane indicate the impact of this observation.

After removing the evidence from the Time Monitor, we can perform Influence Analysis on Target again in order to see the probability of Your Bag on Plane=True as a function of Time, given Your Bag on Carousel=False and Colleague’s Bag on Carousel=True. To focus our analysis on Time alone, we select the Time node and then select Analysis > Visual > Influence Analysis on Target.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-08-06\_17-42-331.jpg)

As before, we select the True tab in the resulting window to see the evolution of probabilities given Time.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/4-Probabilistic\_Reasoning-web-resources/image/2015-08-06\_17-45-131.jpg)

### Summary&#x20;

This chapter provided a brief introduction to knowledge modeling and evidential reasoning with Bayesian networks in BayesiaLab. Bayesian networks can formally encode available knowledge, deal with uncertainties, and perform omnidirectional inference. As a result, we can properly reason about a problem domain despite many unknowns.
