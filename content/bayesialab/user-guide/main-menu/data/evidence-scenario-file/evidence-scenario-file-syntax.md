# Evidence Scenario File Syntax

As with BayesiaLab's Dictionaries, the syntax of an [Evidence Scenario File](./) is straightforward. However, we need to distinguish between the syntax for Contemporaneous and Temporal networks:

### Contemporaneous Networks&#x20;

* Each line of an Evidence Scenario File represents one Evidence Scenario.
* Encoding an Evidence Scenario always follows the same pattern, with the node name and the evidence separated by a colon (:). The optional scenario name follows after a double slash (//).\
  `?<NodeName>?:<Evidence>//<ScenarioName>`
* Evidence can be encoded in several ways in an Evidence Scenario File:
  * Hard Evidence:\
    `?<NodeA>?:<State1>//Scenario1`
  * Numerical Evidence: \
    `?<NodeB>?:m{<value>}//Scenario2`
  * Probabilistic Evidence: \
    `?<NodeC>?:p{<StateA>:0.3;<StateB>:0.5;<StateC>:0.2}//Scenario3`
  * Likelihood Evidence: \
    `?<NodeD?:l{<StateX>:1;<StateY>:0.5}//Scenario4`&#x20;
* To encode multiple pieces of evidence in one Evidence Scenario, simply separate the individual pieces of evidence with a semicolon. The scenario name remains at the end of the line, separated by a double slash.

```
?<NodeA>?:<State1>;?<NodeB>?:m{<value>} ;?<NodeC>?:p{<StateA>:0.3;<StateB>:0.5;<StateC>:0.2};?<NodeD>?:l{<StateX>:1;<StateY>:0.5}//Scenario5   
```

### Temporal Networks&#x20;

* For Temporal Bayesian networks, the syntax of the Evidence Scenario File is slightly different. Here, each line in the text file refers to a time step, in which the evidence specified in that line will be applied.
* Each line starts with an integer value that represents the time step, in which the evidence of that line will be set.&#x20;
* Evidence can be encoded in several ways in an Evidence Scenario File:

```
<TimeStep2>;?<NodeName>?:<Evidence>
<TimeStep4>;?<NodeName>?:<Evidence>
<TimeStep19>;?<NodeName>?:<Evidence>
```

* To encode multiple pieces of evidence in one Time Step, simply separate the individual pieces of evidence with a semicolon.

```
<TimeStep3>;?<NodeA>?:<State1>;?<NodeB>?:m{<value>} ;?<NodeC>?:p{<StateA>:0.3;<StateB>:0.5;<StateC>:0.2};?<NodeD>?:l{<StateX>:1;<StateY>:0.5}\Evidence for Step 3
<TimeStep5>;?<NodeA>?:<State3>;?<NodeB>?:m{<value>} ;?<NodeC>?:p{<StateA>:0.1;<StateB>:0.7;<StateC>:0.2};?<NodeD>?:l{<StateX>:0.1;<StateY>:0.5}\Evidence for Step 5 
```

* For Temporal networks, recalling evidence from the Evidence Scenario File is different compared to Contemporaneous networks.
* Now, the time-specific Evidence Scenarios will be set automatically as you perform a temporal simulation.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Evidence-Scenario-File/TemporalSimulationBar.png" alt="" width="188"><figcaption></figcaption></figure>

