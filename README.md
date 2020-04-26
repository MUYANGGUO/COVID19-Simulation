<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>


## COVID-19 Outbreaks Simulation and Analysis by an Extended SEIR Model

>Georgia Tech CSE6730 Project-2

![Authors](https://img.shields.io/badge/authors:-Muyang_Guo,_Dayu_Zhu,_Yibo_Wang-blue.svg)

[![Buildwithpython](https://img.shields.io/badge/Build--With--Python3-9cf?style=for-the-badge&logo=Python)](https://www.python.org/)

### Abstract

Since the first coronavirus (COVID-19) outbreaks in Wuhan, China, the COVID-19 viral disease has swept into at least 184 countries and killed more than 94,000 people.The US has become a new "center" of the outbreaks as the number of confirmed cases climbed over 450000 and the number of death reached to 16000 by 9th April 2020. It is crucial for the public to understand the transmission pattern of the disease and to take proper measures accordingly. 

Groups of scientists in China, German claimed that people who are infected but do not have symptoms, or have not yet developed symptoms, can also infect others. This transmission pattern distinct among other epidemic transmission patterns such as SARS or MERS. Traditional models such as SIR or SEIR may not describe the spread correctly. Thus, an extended SEIR model was proposed and analyzed in this project paper to address the asymtomatic transmission during the incubation period.
ODE, cellular automata and Markov Chain are the three approaches being used to deploy the conceptual models. The simulated results are collected, and analyzed. Real world data is also used to validate the prediction models. 

### Github Repo

Project Github Repo: https://github.gatech.edu/mguo34/COVID-19-Simulation

### Authors

- Muyang Guo

- Dayu Zhu

- Yibo Wang


### Description of the system

Different from most infectious disease, the COVID-19 has a very long incubation period, which can be up to 14 days. During the incubation periods, the patients have no serve symptom, or even no symptom at all, but are still able to deliver the virus to susceptibles. Thus, a traditional susceptible-infected-recovered (SIR) model may not strictly describe the spread of COVID-19. Thus, we introduce the susceptible-exposed-infected-recovered (SEIR) model to simulate the circumstances of the pandemic. 

We start from the very basic SIR model. In the SIR model, each individual has three distinct states: susceptible, infected, and recovered states. In SIR model, we first need to define a time-dependent variable for S, I and R state, and the variables are the fraction of the states in the overall population. That is, let
$$
% \begin{center}
% \begin{eqnarray}
$S_t$ be the fraction of the population that is susceptible at time t;
$I_t$ be the fraction that is infected at t; and
$R_t$ be the fraction that is recovered at t,
% \end{eqnarray}
% \end{center}
$$
where $$S_t + I_t + R_t = 1$$. 

Since COVID-19 has a very long incubation period, which makes it hard to handle. And the no-symptom patients is one of the major channel of the spread of the virus. To model the incubation period, we introduce another state, exposed (E), to the SIR model, and the modified system is the so-called SEIR model.

In SEIR model, the patients who get the virus will first get into the Exposed state. Then, part of the exposed patients will show symptoms and turn to the Infectious state. We use the parameter $\sigma_0$ to model the transition. Then, the system can be describe as
$$
\begin{center}
\begin{eqnarray}
  \dfrac{d\vec{y}}{dt}
  = \dfrac{d}{dt}\left(\begin{matrix}
      S(t) \\
      E(t) \\
      I(t) \\
      R(t)
    \end{matrix}\right)
  & = & \left(\begin{matrix}
      - \tau_0 I(t) S(t) \\
      \tau_0 I(t) S(t)- \sigma_0 E(t) \\
      \sigma_0 E(t) - \dfrac{1}{\kappa_0} I(t) \\
      \dfrac{1}{\kappa_0} I(t)
    \end{matrix}\right)
  \equiv \vec{F}(\vec{y}),
\end{eqnarray}
\end{center}
$$
where $$\vec{y}(t)$$ is the state vector and both $$\tau_0$$, $$\sigma_0$$ and $$\kappa_0$$ are now rate parameters, having units of "fractions per unit time."


### Models

MUYANG GUO CA model: https://github.gatech.edu/mguo34/COVID-19-Simulation/blob/master/Models_Notebooks/part0--ca.ipynb




DAYU ZHU ODE model: https://github.gatech.edu/mguo34/COVID-19-Simulation/blob/master/Models_Notebooks/SEIR_ODE.ipynb




YIBO WANG Markov Chain Model: https://github.gatech.edu/mguo34/COVID-19-Simulation/blob/master/Models_Notebooks/checkpoint2.ipynb



