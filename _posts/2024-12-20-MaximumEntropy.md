---
layout: post
title: Non-thermal Particle from Maximum Entropy
date: 2024-12-20 23:04 +0800
description: Reading note of a few papers, introducing the theoretical framework of maximum entropy 
tags: StochasticAcceleration
categories: reading
---


Recent works proposed a novel model to account for the power-law non-thermal particle accelerated in turbulence ([Zhdankin 2022a](https://ui.adsabs.harvard.edu/abs/2022PhRvX..12c1011Z/abstract), [2022b](https://ui.adsabs.harvard.edu/abs/2022JPlPh..88c1703Z/abstract)). 

### Casimir Invariants and Casimir Momentum

The Vlasov equation gives the dynamical evolution of collisionless plasma,


$$
\begin{equation}
\partial _t f + v \cdot \nabla f = -F\cdot \frac{\partial  f}{\partial p}
\end{equation}
$$

where LHS is the convective derivative, and RHS is the force, including the EM term and external term. $$f$$ is the particle distribution function. 

For a rising function $$g(f)$$ with good enough properties, $$\frac{1}{N}\int d^3x d^3p g(f)$$ is conserved, as long as f is described by Vlasov equation. Thus a set of $$g(f)$$ is called Casimir invariants. A special invariant is found with dimension of momentum: the so called Casimir momentum.


$$
\begin{equation}
p_{c,\chi}(f) = n_0^{1/3} \left(\frac{1}{N} \int d^3x d^3p f^\chi\right) ^{-\frac{1}{3(\chi-1)}},
\end{equation}
$$

where $$\chi>0$$ is a free index. The Casimir momentum is equivalent with the Renyi entropy in its integral of phase space, and thus is a generalized entropy. 
Spacial inhomogeneity will result in decrease of the entropy, while energy injection will produce entropy. 


### Power-Law Particle
With particle number conservation and energy conservation, and from the maximal entropy condition, it naturally leads to  a power-law particle spectrum:


$$
\begin{equation}
f = C[E(p)/E_b+1]^{-\frac{1}{1-\chi_d}}
,\end{equation}
$$

where $$E_b$$ and $$C$$ is the normalization factor from the Lagrange multipliers. 

In relativistic limit, there is 


$$
\begin{equation}
f\xrightarrow{\text{UR}}C(p/p_b+1)^{-\alpha-2}
,\end{equation}
$$

where $$\alpha = (2\chi_d-1)/(1-\chi_d)$$
<!-- , $$C= N(\alpha-1)\alpha(\alpha+1)/8\pi p_b^3$$ and $$p_b = (\alpha-2)\bar{E}/3c$$.  -->

In non-relativistic limit, there is 

$$
\begin{equation}
f\xrightarrow{\text{NR}}C(p^2/p_b^2+1)^{-\alpha-1/2}
,\end{equation}
$$

where $$\alpha = (\chi_d+1)/2(1-\chi_d)$$.

For $$\chi=1$$, $$f$$ returns to the thermal distribution. 

Comparing the maximal $$p_{c,\chi_d}$$ with the $$p_{c,\infty}$$, the physical condition corresponding to certain $$\alpha$$ is 


$$
\begin{equation}
\begin{aligned}
  \eta \left(\frac{\delta B}{B_0}\right)^2\frac{1}{\beta_c} = & \left(\frac{\alpha+1}{\alpha-2}\right)^{\frac{\alpha+2}{3}}-e\\
  \eta \left(\frac{\delta B}{B_0}\right)^2\frac{1}{\beta_c} = & \left(\frac{\alpha-1/2}{\alpha-2}\right)^{\frac{2\alpha+1}{3}}-e
\end{aligned},
\end{equation}
$$

for relativistic and non-relativistic cases respectively. $$\alpha$$ is the particle SED power-law slope, $$\left(\frac{\delta B}{B_0}\right)^2$$ is the strength of turbulence, $$\eta$$ and $$e$$ are coefficients with $$E_{c,\chi_d} \sim eE_0 + \eta F_{\mathrm{free}}$$.

### Summary 

In these works, one of the Casimir invariants is considered, which has the same dimension with momentum. This invariant is related to the Gibbs entropy. From the argument that entropy is maximized in a system, this model naturally produces a power-law particle distribution. Because the Casimir momentum is physically meaningful, physical conditions could be roughly estimated for non-thermal particles with given power-law slope. 