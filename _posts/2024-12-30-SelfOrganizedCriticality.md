---
layout: post
title: On the Self-Organized Criticality in Astrophysics
date: 2024-12-30 00:00 +0800
description: Recently, Zhang et al. 2024 studied the waiting time distribution of GRB221009A afterglow VHE photons. This post is to summarize their findings 
tags: GRB
categories: reading
---

### Introduction
[Bak et al. 1988](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.38.364) discovered the self-organized criticality in many physical systems. At this state, the system is extremely sensitive to small fluctuations, which propagates quickly throughout large range and can cause the so called avalanche. They used a sand pile model to explain such picture. Increasing the slope of the sand pile somewhere will cause the pile to slide off once the slope is larger than a critical value. They have found that this picture can explain the widely observed 1/f noise, and can also applied to explain the Kolmogorov turbulence model. With random fluctuations, the scale of avalanche, or the lifetime, follows a power-law distribution. This feature is indicative of the SOC properties of the system.

Recently [Zhang et al. 2024](https://arxiv.org/abs/2412.16052) studied the waiting time distribution (WTD) of 147 TeV photons of the Brightes-Of-All-Time gamma-ray burst GRB 221009A, detected by LHAASO KM2A. They have found that the WTD is close to a power-law instead of exponential distribution of independent random events. Also, they have fitted the WT difference with Tsallis q-Gaussian distribution, which also yield a consistent q despite its deviation from the relation with power-law slope. They have concluded that light signals from GRB 221009A is not completely independent, and may exhibit some SOC properties. 

### Self-Organized Criticality
Bak et al. built up a sand pile model and investigated its properties. They assumed that sand has a critical slope $$z_c$$, beyond this value the sand will slide down to lower place. They have found that for the 1-D case, there is a minimally stable state, with everywhere has the same slope $$z_c$$, that is attractor of the system. For a system at this state, if we put another sand on the top of the pile, it will increase the $$z$$ where it is, then slide to next point where it again increases the $$z$$... Finally it will fall down to the edge or where $$z<z_c$$. 

However, it's not the case when extended to 2- or 3-D situations. Since in a multi-dimensional case, each spacial point is in correlation with multiple other points, any fluctuation will propagate to their neighbors. Therefore, the minimally stable state is unstable, as any perturbation will trigger an avalanche with the scale of the minimally stable cluster. 

The 2-D and 3-D bounded numerical experiment yielded power-law distribution of both slide size and slide lifetime. This will explain the observed 1/f noise, where the power spectrum is $$S(f) \propto f^{-2+\alpha}$$. Here f is the frequency of the noise, and $$\alpha$$ is the power-law slope of the lifetime distribution. 

### Waiting Time Distribution of GRB 221009A VHE Photons

The distribution of $$dT_n = T_{n+1}-T_n$$ could be fitted with a power-law function with threshold. Also, the difference of $$dT_n$$, i.e. $$x_i = (dT_{i+n}-dT_i)/\sigma_i$$ could be fitted with a Tsallis q-Gaussian function. For different n, the parameter of q-Gaussian function is constant. However, the WTD power-law slope $$\alpha$$ and the q-Gaussian index $$q$$ does not agree with the theoretical relation $$\alpha = 2/(q-1)$$. 

