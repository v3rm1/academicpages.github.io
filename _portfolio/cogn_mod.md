---
title: "Cognitive Modelling: Basic Principles and Methods"
excerpt: "<br/><img src='/images/portfolio_imgs/cogn_mod_basics.jpg'><br>Assignments and Project work for the Cognitive Modelling course offered under the MSc AI program at the University of Groningen"
collection: portfolio
---
[View Project on Github](https://github.com/v3rm1/cogn_mod_basic)

## Introduction

We attempt to model an ACT-R(Adaptive Control of Thought - Rational) agent[[1]](#1) to study how the model performs in a timing experiment based on the experiment carried out by Jazayeri and Shadlen[[2]](#2).

Temporal learning is modelled as a Bayesian Process[[3]](#3) with prior experiences affecting the perception of future temporal signals. Time perception is seen to compose of a memory component. It has been obesrved that differences in the stimulus cause contamination of the representation of time in the memory [[2]](#2).

Such interferences can be easily observed in real life experiments, with participants unable to differentiate between differnet representations of time[[4]](#4).

---

## Experiment Design

In their experiment, [[2]](#2) tasked participants with reproducing time intervals which were sampled from different uniform distributions. Participants were given feedback after each trial. The subjects depicted higher variability for shorter time intervals as compared to longer time intervals, and the general tendency exhibited a regressional tendency to the mean of the distributions used in the stimulus phase.

In our experiment, we alter the previous experiment, utilizing highly skewed base distributions for sampling stimulus signal times from for the second block of the experiment. We also do not provide the participant any feedback as to how the responses differed from the stimulus time. Participants were split into two groups, one group experiencing more samples from shorter time durations and the other experiencing more samples from the long durations. Participants take a break after an initial set of trials before providing responses to the skewed samples. We expect a general increase in the response times and also, that both groups dpict different priors based on the stimulus distribution.

The participants for the experiment were students of the course and the experiment was carried out in a classroom environment.

Finally the ACT-R model is developed based on the data of the dxperiment.

---

## Model

The model is built in python using the ACT-R theoretical framework. The model resembled the real-life experiments as closely as possible.

---

## Results

Participant data was skewed, with the participants depicting no effects from the manipulation of stimulus. The model, however, depicted clearly the expected skew in outputs discussed in the experimentation section.

---

## References
<a id="1">[1]</a>
Anderson, J. R., Bothell, D., Byrne, M. D., Douglass, S., Lebiere, C., & Qin, Y. (2004). An integrated theory of the mind. Psychol Rev, 111(4), 1036–1060.

<a id="2">[2]</a>
Jazayeri, M., & Shadlen, M. N. (2010). Temporal context calibrates interval timing. Nature Neuroscience, 13(8), 1020–1026.

<a id="3">[3]</a>
Jones, M., & Love, B. C. (2011). Bayesian fundamentalism or enlightenment? On the explanatory status and theoretical contributions of Bayesian models of cognition. Behavioral and Brain Sciences, 34(4), 169.
