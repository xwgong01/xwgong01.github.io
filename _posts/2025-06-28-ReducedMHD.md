---
layout: post
title: Reduced MHD and Derivation of Strauss Equations
date: 2025-06-28 00:00 +0800
description: Reduced MHD is a simplification of the full MHD equations under assumption of strong unidirectional mean field and incompressibility. It was first developed by Strauss 1976, and Kadomtsev & Pogutse 1974.
tags: MHD 
categories: reading
---

### Reduced MHD Equations:

In [S76](https://courses.physics.ucsd.edu/2021/Spring/physics218c/AA_Strauss_RMHD.pdf), the basic MHD equations are

$$\nabla \times \mathbf{B} = \mathbf{j},\, \nabla \cdot \mathbf{B} = 0,$$

the induction equation 

$$\frac{\partial B}{\partial t} = \nabla \times \mathbf{v} \times\mathbf{B}$$

and the momentum equation

$$\rho \frac{\mathrm{d}\mathbf{v}}{\mathrm{d}t} = \mathbf{j}\times \mathbf{B}-\nabla p$$

where  the viscosity is ignored. Here the total magnetic field $$\mathbf{B} = \mathbf{B}_z + \mathbf{B}_\perp$$. As the mean field is along z axis, there is $$B_\perp/  B_z= \varepsilon \ll 1$$. $$\mathbf{v}$$ is the perturbed velocity field, which is also of order $$\varepsilon$$. In the derivation, full MHD equations are simplified with perturbative method, keeping only the low order terms of $$\varepsilon$$.

Since $$k_\parallel \ll k_\perp$$, the variation along z axis is much slower than perpendicular to the magnetic field. Therefore, $$\partial_\perp \sim 1$$ and $$\partial_\parallel \sim \varepsilon$$.

There are also $$B_\perp \sim \varepsilon,\,$$ $$ B_\parallel \sim 1+\varepsilon^2, \, $$ $$j_\perp \sim \varepsilon^2, \,  $$ $$j_\parallel \sim \varepsilon, \, $$ $$p\sim \varepsilon^2, \, $$ $$\rho \sim 1, \, $$ $$v\sim \varepsilon, \ ,$$ $$\partial_t \sim \varepsilon$$.

If we write the magnetic field as 

$$ B = \nabla A_z \times \hat{z} + B_z \hat{z}$$

and take the divergence, the first term vanishes, and we therefore have the divergence of magnetic field 

$$\nabla  \cdot B = \partial _z B_z \sim \varepsilon^3 \approx 0.$$

Integrate the induction equation, one yields

$$\frac{\partial }{\partial t} \mathbf{A}\times \hat{z} = -B_z \mathbf{v} + \nabla \phi \times \hat{z} = 0$$

we are able to define $$\mathbf{v} = \nabla U\times \hat{z}$$, with $$B_z U = \phi$$ the gauge potential. Then there is 

$$\frac{\partial A_z}{\partial t} + \mathbf{v} \cdot \nabla A_z = B_z \frac{\partial U}{\partial z}$$

Using $$\mathbf{j} = \nabla \times \mathbf{B}$$, and substitute $$\mathbf{B}$$ with $$\nabla A_z \times \hat{z} + B_z\hat{z}$$, the current could be written as  

$$j_z = -\nabla^2 A_z,\ \mathbf{j}_\perp = \nabla B_z \times \hat{z} + \nabla_\perp \frac{\partial A}{\partial z}$$. Substitute this in the momentum equation, and similar for the induction equation, one can derive the Strauss equations:

$$\begin{equation}
    \begin{aligned}
        \frac{\partial v}{\partial t} + \mathbf{v}\cdot \nabla_\perp \mathbf{v} = \mathbf{b}\cdot \nabla_\perp \mathbf{b} + B_0 \frac{\partial\mathbf{b}}{\partial z} - \nabla_\perp p + \nu \nabla^2_\perp \mathbf{v},\\
        \frac{\partial \mathbf{b}}{\partial t} + \mathbf{v}\cdot \nabla_\perp \mathbf{b} = \mathbf{b}\cdot \nabla_\perp \mathbf{v} + B_0 \frac{\partial \mathbf{v}}{\partial z} + \eta \nabla^2_\perp \mathbf{b}
    \end{aligned}
\end{equation}$$

here $$\mathbf{b}$$ is the perturbed magnetic field, $$B_0$$ is the mean field. The terms $$\nabla^2_\perp v, \quad \nabla^2_\perp b$$ are due to viscosity, which does not appear in the original paper of Strauss. 

Using the Elsasser variable $$z_\perp^\pm = v_\perp \pm b_\perp$$, the Strauss equations can further be simplified as 

$$\partial_t z^\pm _\perp \mp v_A\nabla _\parallel z^\pm _\perp + z^\mp_\perp \cdot \nabla _\perp z^\pm _\perp =  -\nabla_\perp p + \eta \nabla^2_\perp z^\pm _\perp + f^\pm$$

with the last term on the rhs the external body force. 

From the above RMHD equations, one can notice that the Elsasser variable z is the normal coordinate of the system. The solution of each equation without the nonlinear term $$z \cdot \nabla_\perp z$$ is a Alfvenic wave packet, with $$z^+$$ propagating along and $$z^-$$ reverse to the mean field. The MHD turbulence in incompressible plasma can therefore be regarded as encounters of Alfvenic wave packets with opposite propagation direction. 

### Goldreich-Sridhar Spectrum, Critical Balance and Scale-dependent Anisotropy

Consider a wave A interacting with a 2d fluctuation and produces the third wave B, which is called three-wave interaction. In this process, wave vector and frequency are conserved, i.e. 

$$\begin{aligned}
    \mathbf{k}_A + \mathbf{k}_{2D} =\mathbf{k}_B\\
    \omega^\mp_A + \omega^\pm_{2D} = \omega^\pm{B} 
\end{aligned}$$

Since for 2D perturbation, the parallel wave number is zero, there is $$ k_{\parallel, B} = k_{\parallel, A}$$ and $$k_{\perp, B} = k_{\perp, A} + k_{\perp, 2D}$$. In this way, wave cascade will result in larger $$k_\perp$$ and unchanged $$k_\parallel$$. In presence of strong mean field, the cascade is anisotropic.

But this is based on the assumption that Alfven wave packet exhibit wave-like behavior, i.e. the alfven timescale $$\tau_A \equiv l_\parallel / v_A$$ is much shorter than the nonlinear timescale, which could be defined as equivalent to the eddy turnover timescale here, $$\tau_{nl}^\pm \sim \lambda / \delta z^\mp_\lambda$$. $$\lambda$$ here is the perpendicular scale, and since a wave packet will interact with another opposite propagating wave, the nonlinear timescale depends on how fast the opposite wave passes the scale of interest. 

 Under the anisotropic cascade, $$\lambda$$ gets always smaller, while $$l_\parallel$$ is kept unchanged (this is indeed not true and will be discussed with more rigor), so eventually the condition $$\tau_A \ll \tau_{nl}$$ will no longer be satisfied, and the perturbation resembles isotropic Kolmogorov-like turbulence (detail see Appendix A of [Lazarian et al 1999](https://arxiv.org/pdf/astro-ph/9811037)).

Critical balance is therefore a natural result, where $$\tau_A \sim \tau_{nl}$$. Therefore, the energy flow (or energy dissipation rate) in wavenumber k space is 

$$\varepsilon^\pm \sim  \frac{(\delta z^\pm_\parallel)^2}{\tau_A}$$


$$\delta z_\parallel ^\pm = \left(\frac{l_\parallel \varepsilon^\pm}{v_A}\right)^{1/2} \Rightarrow E(k_\parallel) \sim \frac{(\delta z_\parallel ^\pm )^2}{k_\parallel} = \frac{\varepsilon^\pm}{v_A} k_\parallel^{-2}$$

In the calculation of $$E$$ we have used the fact that z has the dimension of velocity.

Now consider the perpendicular nonlinear timescale 

$$\tau^\pm _{nl}\sim \frac{\lambda}{\delta z^\mp_\lambda},$$ 

and

$$\varepsilon^\pm = \frac{(\delta z^\pm_\lambda)^2}{\tau^\pm_{nl}} \Rightarrow  \delta z^\pm_\lambda = (\tilde{\varepsilon}^\pm \lambda)^{1/3}, \tilde{\varepsilon} \equiv \frac{(\varepsilon^{\pm})^2}{\varepsilon^\mp}.$$

Therefore,

$$E(k_\perp) \sim( \tilde{\varepsilon}) ^{2/3} k_\perp^{-5/3}$$

and compare these two equations of $$E$$, we have the scale-dependent anisotropy $$k_\parallel \propto k_\perp^{2/3}$$.

Above is the model proposed by [Goldreich & Sridhar 1995](https://ui.adsabs.harvard.edu/abs/2000PhRvL..85.4656C/abstract), which agrees with the Kolmogorov 5/3 law, but with anisotropic cascade. The GS95 model, however, is based on the overall mean field. The exact treatment should consider the coarse-grained local magnetic field on scale $$\lambda$$. Therefore the anisotropy $$k_\parallel \propto k_\perp^q$$ measured in numerical simulations is between $$q = 2/3$$ and $$q = 1/2$$. 

### Boldyrev's Theory, 3D Eddy

[Boldyrev 2006](https://https://arxiv.org/pdf/astro-ph/0511290) proposed a modification to the GS95 model by considering the dynamical alignment effect. The velocity and magnetic fluctuation has two conserved integrals, i.e. the energy integral 

$$E = \int \frac{|v^2 + b^2|}{2} \mathrm{d}V$$

and cross-helicity

$$H = \int |\mathbf{b}\cdot \mathbf{v}| \mathrm{d}V.$$

Without driving force, the former will decay quickly due to viscosity of the plasma (that's what happens by wave cascade), but the latter decays slower because there is no definite direction of decay. Therefore, magnetic and velocity perturbation will eventually tend to be parallel and anti-parallel, i.e. $$\mathbf{b} \sim \pm\mathbf{v}$$. We can write the angle in the horizontal plane (perpendicular to the mean field $$B_0$$) as $$\theta_\lambda$$ on scale $$\lambda$$. The perpendicular scale of the eddy is then the relative separation during the Alfven crossing time, considering the small angle between v and b,  

$$\lambda = \frac{l_\parallel \delta v_\lambda \theta_\lambda}{v_A}$$

and the field line separation is calculated with the full velocity fluctiation $$\delta v_\lambda$$,

$$\xi = \frac{l_\parallel \delta v_\lambda}{v_A}.$$

Then the eddy has a 3-dimensional shape, with parallel scale $$l$$, perpendicular scale $$\lambda$$ and magnetic field separation $$\xi$$, and for small $$\theta_\lambda$$, there is $$l \gg \xi \gg \lambda$$. This is different here from the axis-symmetric eddy in GS95 model, where $$\delta v$$ and $$\delta b$$ are assumed perpendicular to each other, and therefore $$\theta_\lambda = 0$$, $$\xi = \lambda$$. 

For small $$\theta_\lambda$$, the non-linear term in RMHD equation $$z^\mp \cdot \nabla z^\pm$$ is smaller, because one of the $$z$$ is small. Dynamical alignment therefore weakens the nonlinear interaction. Since $$\theta_\lambda$$ is an unknown parameter, the author modeled it with a power-law function of $$\lambda$$, 

$$\theta_\lambda \propto \lambda^{\frac{\alpha}{3+\alpha}},$$

this assumption is equivalent to assuming scale-invariant fluctuation. It's then straightforward to obtain 

$$\xi \propto \lambda^{\frac{3}{3+\alpha}},\quad \delta v_\lambda \propto  \lambda^{\frac{1}{3+\alpha}}, \quad l_\parallel  \propto  \lambda^{\frac{2}{3+\alpha}}.$$

The second and third scaling have used the assumption of static turbulent spectrum, i.e. $$\varepsilon^\pm = \delta v_\lambda^2 / \tau_A = Const.$$, so $$l_\parallel \propto \delta v_\lambda^2 $$. 

GS95 model corresponds to the case $$\alpha = 0$$. To specify $$\alpha$$, we need to choose the $$\alpha$$ that makes $$v$$ and $$b$$ most aligned. The angle between $$v$$ and $$b$$ can be written as $$\phi \sim \sqrt{\theta_\lambda^2 + \tilde{\theta}_\lambda^2}$$, where $$\theta_\lambda \sim \lambda / \xi$$ is the perpendicular angle, and $$\tilde{\theta}_\lambda \sim \xi / l_\parallel $$ is the angle in vertical plane. 
Limit $$\alpha \to 0$$ leads to large $${\theta}_\lambda$$, while $$\alpha \to \infty $$ leads to large $$\tilde{\theta}_\lambda$$. The value to minimize $$\phi$$ is $$\alpha = 1$$, and therefore 

$$\xi \propto \lambda^{3/4},\quad \delta v_\lambda \propto \lambda^{1/4},\quad l_\parallel \propto \lambda ^{1/2}.$$

The scaling of $$E(k_\perp)$$ is therefore


$$E(k_\perp) \sim \delta v^2 k_\perp \propto k_\perp ^{3/2}.$$

This returns to the Iroshnikov-Kraichnan scaling, except that this is an anisotropic version. 






