---
layout: post
title: On the Self-Organized Criticality in Astrophysics
date: 2024-12-30 00:00 +0800
description: Recently, Zhang et al. 2024 studied the waiting time distribution of GRB221009A afterglow VHE photons. This post is to summarize their findings 
tags: GRB
categories: reading
---

### Introduction
[Bak et al. 1988](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.38.364) discovered the self-organized criticality in many physical systems. At this state, the system is extremely sensitive to small fluctuations, which propagates quickly throughout large range and can cause the so called avalanche. They used a sand pile model to explain such picture. Increasing the slope of the sand pile somewhere will cause the pile to slide off once the slope is larger than a critical value. They have found that this picture can explain the commonly observed 1/f noise, and can also applied to explain the Kolmogorov turbulence model. With random fluctuations, the scale of avalanche, along with the avalanche lifetime, follows a power-law distribution. This feature is indicative of the SOC properties of the system.

Recently [Zhang et al. 2024](https://arxiv.org/abs/2412.16052) studied the waiting time distribution (WTD) of 147 TeV photons of the Brightes-Of-All-Time gamma-ray burst GRB 221009A, detected by LHAASO KM2A. They have found that the WTD is close to a power-law instead of exponential distribution of independent random events. Also, they have fitted the WT difference with Tsallis q-Gaussian distribution, which also yield a consistent q despite its deviation from the relation with power-law slope. They have concluded that light signals from GRB 221009A is not completely independent, and may exhibit some SOC properties. 

### Self-Organized Criticality
Bak et al. built up a sand pile model and investigated its properties. They assumed that sand has a critical slope $$z_c$$, beyond this value the sand will slide down to lower place. For the 1-D case, i.e. sand could only slide in two directions to their neighbor points, there is a minimally stable state, with the same slope $$z_c$$ for every points. The minimally stable state is, according to Bak, an attractor of the system. For a system at this state, if another sand grain is dropped on the top of the pile, it will increase the $$z$$ at that location where it is dropped, then slide to next point where it again increases the $$z$$... Finally it will fall down to the edge or the slide will stop where $$z<z_c$$. 

However, it's not the case when extended to 2- or 3-D situations. Since in a multi-dimensional case, each spacial point is in correlation with multiple points, any fluctuation will propagate to their neighbors (i.e. each point has 4 neighbors in 2D case). Therefore, the minimally stable state in the 1D scenario is not stable any more, as any perturbation will trigger an avalanche with the scale of the minimally stable cluster. 

The 2-D and 3-D bounded numerical experiment yielded power-law distribution of both slide size and slide lifetime. This will explain the observed 1/f noise, where the power spectrum is $$S(f) \propto f^{-2+\alpha}$$. Here f is the frequency of the noise, and $$\alpha$$ is the power-law slope of the lifetime distribution. 

### Waiting Time Distribution and Astrophysical Application

In astrophysical events, such as gamma-ray bursts, photons are treated as originated from a point source, regardless of the spatial location of photon emission. Thus by statistics of the waiting time (the time interval between detection of two events) could be used to yield information of randomness of photon emission. If events are randomly generated, i.e. from a SOC system, the avalanche induced is fully independent of the initial perturbation. In such a case, photons all follow a Poisson distribution. For a continuously changing emission rate, the waiting time distribution is thus a superposition of separate exponential distribution, which results in many cases in a power-law WTD. While other mechanisms can also produce similar power-law properties as SOC process, they could be distinguished by the statistics of waiting time. SOC process are random and spacial independent, e.g. earthquakes. However, the aftershock occurs around each earthquake, with a Dirac-$$\delta$$ like spacial distribution at each earthquakes. The influence of such spacial dependence will be reflected in WTD, i.e. for events with clusterization, the power-law slope of WTD will be $$p\sim 2$$, while for gradually varying events, $$p\lesssim 3$$. 

For flaring stars, the variability timescale are small, which is assumed due to flares and micro-flares. Given the low counts rate, waiting time statistics of single photons instead of each flare are studied. 
Another example is the black hole accretion disk, where variability timescales are at 10 ms. WTD of such peaks follow Poisson statistics, indicating the peaks originate from a SOC process. Indeed, theoretical model of reservoir agrees with the detected WTD. It is assumed that as soon as mass in the reservoir exceed a critical value, it collapses inward, inducing an avalanche and produces a peak in the light curve by Bremsstrahlung. After each big pulse, mass needs time to cumulate in the reservoir in order to produce next pulse. Though observed WTD deviates from the simple stationary Poisson process, it might not contradict to the SOC picture if modification from additional effects such as size limit, time variability and spacial inhomogeneity are considered.


### Waiting Time Distribution of GRB 221009A VHE Photons

The distribution of $$dT_n = T_{n+1}-T_n$$ could be fitted with a power-law function with threshold. Also, the difference of $$dT_n$$, i.e. $$x_i = (dT_{i+n}-dT_i)/\sigma_i$$ could be fitted with a Tsallis q-Gaussian function. For different n, the parameter of q-Gaussian function is constant, revealing some scale invariance. Yet, the WTD power-law slope $$\alpha$$ and the q-Gaussian index $$q$$ does not agree with the theoretical relation $$\alpha = 2/(q-1)$$. As the power-law distribution is indicative of the self-organized criticality, this deviation might due to the lack of independence of photons, according to the authors. 

In a structured jet model, GRB 221009A is thought to have a Poynting-flux-dominated core and a matter-dominated wing. Photons from the core is produced by magnetic dominated processes, which corresponds to some SOC systems. Though the conclusion in this work is not very strong, it provides a new perspective of the holistic characteristics of the system as a supplement to conventional spectral and temporal analysis.
