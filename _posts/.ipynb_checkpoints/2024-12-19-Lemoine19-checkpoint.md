---
layout: post
title: Generalized Fermi Acceleration Reading Note
date: 2025-03-05 12:30 +0800
description: Reading note of Lemoine 2019 PhRvD, the theoretical framework of generatlized Fermi acceleration
tags: StochasticAcceleration
categories: reading
---


## Kinetic Equation

Electro-magnetic field is boosted to the frame in which electric field vanishes. This frame is not necessarily coincident with the fluid comoving frame unless ideal MHD is assumed. So the author defined a comoving locally inertial frame $$\mathcal{\hat{R}}_u$$ In the particle comoving frame, the kinetic equation is written as


$$
\begin{equation}
\frac{\mathrm{d} \hat{p}^{\hat{a}}}{\mathrm{d}\tau} =
\frac{q}{m} \hat{F}^{\hat{a}} _{\hat{ b}}\hat{p}^{\hat{b}} - \hat{\Gamma}^{\hat{a}}_{\hat{b}\hat{c}}\frac{\hat{p}^{\hat{b}}\hat{p}^{\hat{c}}}{m}
,\end{equation}
$$


$\begin{equation}
\frac{\mathrm{d} \hat{p}^{\hat{a}}}{\mathrm{d}\tau} =
\frac{q}{m} \hat{F}^{\hat{a}} _{\hat{ b}}\hat{p}^{\hat{b}} - \hat{\Gamma}^{\hat{a}}_{\hat{b}\hat{c}}\frac{\hat{p}^{\hat{b}}\hat{p}^{\hat{c}}}{m}
,\end{equation}$


where the first term leads to pitch angle diffusion by electromagnetic field tensor, without changing the particle energy. The second term is the local coordinate, which changes with time and accelerates particle. The quantities with hat represent those in local inertial frame of particle. 

### Spin Connection

The $$\hat{\Gamma}^{\hat{a}}_{\hat{b}\hat{c}}$$ here is the connection of the tetrad, which is defined as $$\hat{\Gamma}^{\hat{a}}_{\hat{b}\hat{c}} =-e_{\hat{b}}^\beta e_{\hat{c}}^\gamma e^{\hat{a}}_{\beta;\gamma}$$, and the $$e^{\hat{a}}_{\beta;\gamma}$$ is covariant derivative of the tetrad. For a simple example, we now assume a flat space-time of both lab frame and LIF, so the tetrad coefficients are just the Lorentz transformation matrix, with $$u^x$$ the only non-zero spatial component of 4-velocity , i.e. 


$$
\begin{equation}
e_\alpha^{\hat{a}} = \Lambda_\alpha^{\hat{a}} = \begin{bmatrix}
u^t&-u^x&0&0&\\
-u^x&u^t&0&0\\
0&0&1&0\\
0&0&0&1
\end{bmatrix}\label{conn}
\end{equation}
$$



and the inverse transformation is obtained by substituting $$-u^x$$ with $$u^x$$. 

Then we can simply compute the coefficients, e.g. 
$$\hat{\Gamma}_{\hat{1}\,\hat{0}}^{\hat{0}} = -e_{\hat{1}}^\beta e_{\hat{0}}^\gamma e^{\hat{0}}_{\beta;\gamma}$$
 Substitute the above \eqref{conn} into this equation, we obtain (for $$\{(\beta, \gamma)\} \in \{(0,0),\,(1,0),\,(0,1),\,(1,1)\}$$)
 $$\hat{\Gamma}_{\hat{1}\,\hat{0}}^{\hat{0}} = -u^xu^tu^t_{,t} + (u^t)^2 u^x_{,t} - (u^x)^2 u^t_{,x} + u^xu^tu^x_{,x}$$. Then we differentiate the normalization of 4-velocity u $$(u^t)^2-(u^t)^2 = 1$$, so $$u^t u^t_{,a} = u^x u^x_{,a}$$ and then simplify the above equation, we get 
 $$\hat{\Gamma}_{\hat{1}\,\hat{0}}^{\hat{0}} = u^x_{,t} + \beta u^x_{,x}$$.

 This is the simplest example of computing the connection coefficient. Though the geometry of lab frame may be non-trivial, the calculation of the connection follows the same procedure. 



## Energy Gain

$$
\begin{equation}
\Delta p^t(\Delta \tau) = [e^t_{\hat{a}}(\Delta \tau)- e^t_{\hat{a}}(0)]\hat{p}^{\hat{a}}(0) + e^t_{\hat{a}}(\Delta \tau)\int_0^{\Delta\tau} \mathrm{d}\tau_1 \frac{\mathrm d \hat{p}^{\hat{a}}}{\mathrm{d}\tau _1}
\end{equation}
$$

Here the first term describes Fermi acceleration, and second term is the particle kinetic evolution in its local frame. \hat{\beta}
$$e^t_{\hat{a}} $$
is the Vierbein of relativistic transformation, which is defined by $$g_{\mu\nu} = e^{\hat{\alpha}}_\mu e^{\hat{\beta}}_\nu \eta_{\hat{\alpha}\hat{\beta}}$$. 

As an application of this framework, the conclusions of shock acceleration could be reproduced (in Section II).

## Non-resonant acceleration
The second-order moment has two components, one from frame transformation and the other from particle trajectory. The first term is defined as 


$$
\begin{equation}
\Delta_{0}^{2} \equiv \langle [e^{t}_{\hat{a}}(\Delta\tau) - e^{t}_{\hat{a}}(0)][e^{t}_{\hat{b}}(\Delta\tau) - e^{t}_{\hat{b}}(0)]\hat{p}^{\hat{a}}(0)\hat{p}^{\hat{b}}(0) \rangle,
\end{equation}
$$

which could be evaluated as 

$$
\Delta_{0}^{2} \approx p(0)^{2} \left\{ \begin{array}{ll}
\frac{4}{3}\beta_{u}^{2} & (\gamma_{u}^{2}\beta_{u}^{2} \ll 1), \\
2\gamma_{u}^{4} & (\gamma_{u}^{2}\beta_{u}^{2} \gg 1).
\end{array} \right.
$$

**I do not know how this is derived (the coefficients I got were different)**, but I guess the non-relativistic and ultra-relativistic results come from the Lorentz boosted momentum in the LIF. For simplicity we assume a flat lab frame, and $$u$$ is initially along $$x$$ direction, so the tetrad is simply Lorentz transformation tensor in x direction. Thus, 

$$\hat{p}^{\hat{a}}(0)=e_\alpha^{\hat{a}}\, p^a = \left\{
\begin{array}{ll}
    u^t(0)p^0(0) + u^x(0)p^x(0)\\
    u^x(0)p^0(0) + u^0(0)p^x(0)
\end{array}\right.
$$

We assume that initial $$p$$ is in random direction, so $$\langle {p^{x}}^2\rangle = p^2/3$$, and the average of spatial components of $$u^i(\Delta \tau)= u^2/3$$ with $$i = x,y,z$$. Then the above $$\Delta_0^2 = A_1\gamma^2\beta^2 p^2 + A_2\gamma^4\beta^2 p^2$$, where it could be approximated in non-relativistic and ultra-relativistic limits.

**A problem:**  The Lorentz transformation tensor is written as (eq. 3), but when I set $$u^x = u^y = 0$$, it cannot degrade to the Lorentz transformation in $$x$$ direction. Why??

$$
\begin{aligned}
& \Lambda^{\bar{0}}_{\bar{0}}(\mathbf{x}) = \bar{u}^{\bar{0}}(\mathbf{x}), \quad \quad \Lambda^{\bar{0}}_{\bar{i}}(\mathbf{x}) = \bar{u}_{\bar{i}}(\mathbf{x}), \\
& \Lambda^{\bar{i}}_{\bar{0}}(\mathbf{x}) = \bar{u}^{\bar{i}}(\mathbf{x}), \quad \quad \Lambda^{\bar{i}}_{\bar{j}}(\mathbf{x}) = \delta^{\bar{i}}_{\bar{j}} + \frac{\bar{u}^{\bar{i}}(\mathbf{x})\bar{u}_{\bar{j}}(\mathbf{x})}{1 + \bar{u}^{\bar{0}}(\mathbf{x})}.
\end{aligned}
$$

The energy diffusion coefficient is

$$
\begin{aligned}
\left\langle \frac{\Delta p^{t} \Delta p^{t}}{2\Delta t} \right\rangle =&\lim_{\Delta t \to +\infty} \frac{1}{2\Delta t} 
\left\langle e^{t}_{\hat{a}}(\Delta\tau)e^{t}_{\hat{b}}(\Delta\tau) \int_{0}^{\Delta\tau} \mathrm{d}\tau_{1} \mathrm{d}\tau_{2} \frac{\mathrm{d}\hat{p}^{\hat{a}}}{\mathrm{d}\tau_{1}} \frac{\mathrm{d}\hat{p}^{\hat{b}}}{\mathrm{d}\tau_{2}} \right\rangle\\
=& \lim_{\Delta t \to +\infty} \frac{1}{2\Delta t} \int \mathrm{d}\tau_1 \mathrm{d}\tau_2 \gamma_{u}^{2} \left( 1 + \frac{1}{3}\beta_{u}^{2} \right)  \times \left\langle \frac{\mathrm{d}\hat{p}^{0}}{\mathrm{d}\tau_1} \frac{\mathrm{d}\hat{p}^{0}}{\mathrm{d}\tau_2} \right\rangle.
\end{aligned}
$$

where $$e^t_{\hat{a}} = -u_a$$ and $$\langle\Delta \hat{p}^{\hat{i}}\Delta\hat{p}^{\hat{j}}\rangle = \eta_{\hat{i}\hat{j}}\langle \Delta p^{\hat{0}}\Delta p^{\hat{0}}\rangle/3$$ are used. 


### Turbulence Description

It is assumed that the 4-order moment could be expressed with second order monment (property of the Gaussian random field),

$$\langle u^iu^ju^ku^l\rangle=\langle u^iu^j\rangle\langle u^ku^l\rangle+\langle u^iu^k\rangle\langle u^ju^l\rangle+\langle u^ju^k\rangle\langle u^iu^l\rangle$$

And the derivative $$u^i_{,j}$$ could also decompose into 

$$u^i_{,j} = \frac{1}{3}\delta^i_j\theta + \sigma^i_j + \omega^i_j$$,

with $$\theta = \partial_i u^i$$ the divergence of 4-velocity, 

$$\sigma_{ij}=\sigma_{ji} = \frac{1}{2}(u_{i,j}+u_{j,i})-\frac{1}{3}\delta_{ij}\theta$$ is the shear tensor and 

$$\omega_{ij} = -\omega_{ji} = \frac{1}{2}(u_{i,j}-u_{j,i})$$


### Correlation

And for $$I\in\{\theta, \omega,u,\sigma, a\}$$, there are correlation functions with form

$$
\begin{aligned}
C_{I}(\mathbf{x}_{1}; \mathbf{x}_{2}) &= \exp \left[ -\frac{\pi}{4}\Omega_{I}^{2}(t_{1} - t_{2})^{2} - \frac{\pi}{4}K_{I}^{2}(\mathbf{x}_{1} - \mathbf{x}_{2})^{2} \right]. 
\end{aligned}
$$

For momentum correlation, there is 

$$
\left\langle \hat{p}^{i}(t_{1})\hat{p}^{j}(t_{2}) \right\rangle = \frac{1}{3}\eta^{ij}\hat{p}_1\hat{p}_2C_{p}(t_{1}; t_{2}) \, 
$$

where $$\hat{p}_{1,2} = \hat{p}(\tau_{1,2})$$ and

$$
C_{p}(t_{1}; t_{2}) = \exp \left[ -\frac{\pi}{4} \frac{(t_{1} - t_{2})^{2}}{t_{s}^{2}} \right].
$$

The $$t_s$$ here is the scatter timescale, so if $$t_1-t_2 \gg t_s$$, particle is scattered multiple times, and the momentum $$p(t_2)$$ is not correlated to $$p(t_1)$$ anymore.

### Non-relativistic limit

In the NR regime, $$\gamma \sim 1$$ and only the lowest order of $$\beta$$ is kept. After some tedious algebra, there is 

$$
\begin{split}
\langle \Delta p^2 \rangle = p^2 \int \mathrm{d} t_1 \mathrm{d} t_2 \left\{ \langle \theta ^ 2 \rangle C _ \theta ( t _ 1 , t _ 2 ) \left[ 1 + \frac { 2 } { 3 } C _ p ( t _ 1 , t _ 2 ) ^ 2 \right] \right.\\
\left.
+ \langle a ^ 2 \rangle C _ a ( t _ 1 , t _ 2 ) C _ p ( t _ 1 , t _ 2 ) + \frac { 2 } { 5 } \langle \sigma ^ 2 \rangle C _ \sigma ( t _ 1 , t _ 2 ) C _ p ( t _ 1 , t _ 2 ) ^ 2 \right\} .    
\end{split}

$$

Again, I failed in deriving this equation. My steps are computing 
$$\langle \left(\hat{\Gamma}_{\hat{a}\hat{b}}^{\hat{0}} \hat{p}^{\hat{a}}\hat{p}^{\hat{b}} \right)_{t_1}
\left(\hat{\Gamma}_{\hat{c}\hat{d}}^{\hat{0}} \hat{p}^{\hat{c}}\hat{p}^{\hat{d}}\right)_{t_2}\rangle$$

and use the connection coefficients in the appendix:

$$
\begin{aligned}
\hat { \Gamma } _ { 0 \hat { 0 } } ^ { 0 } & = 0 , & \\
\hat { \Gamma } _ { 0 \hat { i } } ^ { 0 } &= 0 , \\
\hat { \Gamma } _ { i \hat { 0 } } ^ { 0 } & = - \frac { u _ { i } u ^ { \alpha } u _ { k } u ^ { k } { , \alpha } } { \gamma _ { u } ( 1 + \gamma _ { u } ) } + u ^ { \alpha } u _ { i , \alpha } , \\
\hat { \Gamma } _ { i \hat { j } } ^ { 0 } & = - \frac { u _ { i } u _ { j } } { \gamma _ { u } ( 1 + \gamma _ { u } ) } \left( u _ { k } u ^ { k } { , t } + \frac { u ^ { k } u _ { l } u ^ { l } { , k } } { 1 + \gamma _ { u } } \right) + u _ { j } u _ { i , t } + u _ { i , j } + \frac { u _ { j } u ^ { k } u _ { i , k } } { 1 + \gamma _ { u } } - \frac { u _ { i } u ^ { k } u _ { k , j } } { \gamma _ { u } ( 1 + \gamma _ { u } ) } .
\end{aligned}
$$

I only reproduced the first term with compression $$\theta$$. For the second term, there is $$C_p$$ of first order with $$C_a$$. This will require $$\langle p^a(t_1) p^c(t_2) p^0(t_1) p^0(t_2)\rangle$$ as well as $$\langle u^i_{,t}u^j_{,t}\rangle$$, but in term $$\hat{\Gamma}_{i0}^0$$ there is no such term. Also, for the last term with coefficient $$2/5$$, I don't know where does the $$5$$ come from. There are only $$1/\gamma(1+\gamma)=1/2$$ and $$1/3$$ in the coefficients, so $$5$$ could not be produced as it's a prime number.

Anyway, I just followed the results from the paper. 
The compression influences the average over particle population, but a single particle will not be affected (as there are dilation as well). So the contribution from compression is defined separately, 

$$
\begin{aligned}
\langle \Delta p ^ { 2 } \rangle _ { N } & = p ^ { 2 } \int \mathrm { d } t _ { 1 } \mathrm { d } t _ { 2 } \langle \theta ^ { 2 } \rangle C _ { \theta } ( t _ { 1 } , t _ { 2 } ) , \\
\langle \Delta p ^ { 2 } \rangle _ { 1 } & = \langle \Delta p ^ { 2 } \rangle - \langle \Delta p ^ { 2 } \rangle _ { N } .
\end{aligned}
$$

### Three cases

The exponential function in the integral is 

$$
\begin{aligned}
    \exp\left(-\frac{\pi}{4}(\Omega^2 + \frac{4}{9}K^2t_s^2)(t_2-t_1)^2\right) ,& & \langle \Delta p ^ { 2 } \rangle _ { N }\\
    \exp\left(-\frac{\pi}{4}(\Omega^2 + \frac{4}{9}K^2t_s^2 + \frac{1}{t_s^2}) (t_2-t_1)^2\right), && \langle \Delta p ^ { 2 } \rangle _ { 1 }\\
\end{aligned}$$

Here $$(x_1 - x_2) = \frac{2}{3}Kt_s |t_1-t_2|$$ is used. 
Again, I did not get the same coefficients, but the scaling is consistent. 

#### 1. $$\Omega/ K^2 \ll t_s \ll K^{-1}$$

The $$\langle \Delta p ^ { 2 } \rangle _ { N }/2\Delta t$$ is dominated by  $$K^2t_s^2$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { N }}{2\Delta t} \propto\frac{ p^2 }{Kt_s} $$

The $$\langle \Delta p ^ { 2 } \rangle _ { 1 }/2\Delta t$$ is dominated by  $$1/t_s^2$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { 1 }}{2\Delta t} \propto p^2 t_s $$



#### 2. $$\Omega /K^2  \ll K^{-1}\ll t_s$$

The $$\langle \Delta p ^ { 2 } \rangle _ { N }/2\Delta t$$ is dominated by  $$K^2t_s^2$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { N }}{2\Delta t} \propto\frac{ p^2 }{Kt_s} $$

The $$\langle \Delta p ^ { 2 } \rangle _ { 1 }/2\Delta t$$ is dominated by  $$K^2t_s^2$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { 1 }}{2\Delta t} \propto\frac{ p^2 }{Kt_s}$$

#### 3.  $$t_s \ll\Omega /K^2 \ll K^{-1}$$

The $$\langle \Delta p ^ { 2 } \rangle _ { N }/2\Delta t$$ is dominated by  $$\Omega$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { N }}{2\Delta t} \propto\frac{ p^2 }{\Omega} $$

The $$\langle \Delta p ^ { 2 } \rangle _ { 1 }/2\Delta t$$ is dominated by  $$1/t_s^2$$, therefore scales as 

$$\frac{\langle \Delta p ^ { 2 } \rangle _ { 1 }}{2\Delta t} \propto p^2t_s$$
