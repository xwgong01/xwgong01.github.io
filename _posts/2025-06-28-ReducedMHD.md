---
layout: post
title: Reduced MHD and Derivation of Strauss Equations
date: 2025-06-28 00:00 +0800
description: Reduced MHD is a simplification of the full MHD equations under assumption of strong unidirectional mean field and incompressibility. It was first developed by Strauss 1976, and Kadomtsev & Pogutse 1974.
tags: MHD 
categories: reading
---

### MHD equations:

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

