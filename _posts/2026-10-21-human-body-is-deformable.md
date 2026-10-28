---
layout: post
title: "4. Muscle is a heterogeneous, deformable material"
date: 2026-10-22
published: false
---

A perfectly balanced handstand is what we would call the ideal case. The human body, by contrast, is a remarkable organic assembly of tissues that deform under load. Our goal in a handstand is to coordinate all these components so that they work together to — metaphorically speaking — escape gravity (which, physically speaking, is impossible for a body subject to gravity). Therefore, to build a useful model, we must account for the mechanical complexity of the human body.

## A first model and why it doesn't work

To understand what happens within each material, we can explore the continuum mechanics. This branch of mechanics describes the behavior of materials by treating them as continuous media. A common form of the equation of motion — known as Cauchy’s equation of motion — is:

$$
\rho \frac{\partial^2 \mathbf{u}}{\partial t^2} = \nabla \cdot \boldsymbol{\sigma} +\rho \mathbf{f}
$$

I acknowledge the notation is a bit tricky but, in other words, instead of considering only the motion of the whole body through its center of mass, we zoom in on a small region of tissue and examine the local balance of momentum. It is the equivalent of applying Newton’s second law, but on a much smaller scale, showing how every small volume element behaves under external loading and interacts with its neighboring elements (Figure 1):

<figure>
  <img src="{{ '/assets/img/cauchy_local_equation_of_motion.png' | relative_url }}"
       alt="Cauchy local equation of motion">
  <figcaption>
    Figure 1. Cauchy local equation of motion.
  </figcaption>
</figure>

Let’s analyze the individual terms:
where:

$$\rho$$ = mass density of the medium (the tissue) [kg/m^3]<br>
$$\mathbf{u}$$ (or $$u_i$$) = displacement field [m]<br>
$$\boldsymbol{\sigma}$$ = stress tensor [Pa = N/m^2]<br>
$$\nabla \cdot \boldsymbol{\sigma}$$ = divergence of the stress field [N/m^3]<br>
$$\mathbf{f}$$ = external body force per unit mass (e.g., gravity) [N/kg = m/s^2]<br>

Every term of the equation has the dimensions of a force per unit volume (\\( \mathrm{N/m^3} \\)): the inertial term \\( \rho\,\partial^2\mathbf{u}/\partial t^2 \\) (\\( \mathrm{kg/m^3} \times \mathrm{m/s^2} \\)), the stress term \\( \nabla\cdot\boldsymbol{\sigma} \\) (\\( \mathrm{Pa/m} \\)) and the body-force term \\( \rho\,\mathbf{f} \\) (\\( \mathrm{kg/m^3} \times \mathrm{m/s^2} \\)).

This model is useful to show that things are more complicated and that another scale of study exists. Yet, with this model we assume small displacements and small strains, which allows us to write the equation of motion with the simple time derivative \\( \partial^2 \mathbf{u}/\partial t^2 \\). For large deformations, as in a strongly contracting muscle, the exact formulation refers to the reference configuration and uses the first Piola–Kirchhoff stress.

Cauchy's equation is a balance of momentum, so it holds for any material, from a tendon to a block of rubber. What it does not tell us is how the stress \\( \boldsymbol{\sigma} \\) depends on the tissue itself. Bones, muscles, tendons and other tissues of the musculoskeletal system have different mechanical properties. Their internal structure influences how they deform, how they generate or transmit forces, and how they respond to loading. Different tissues do not behave in the same way, nor do they respond on the same timescale.

## Body is viscoelastic: the Hill model

To close the problem we need a **constitutive law**, a rule that links the stress to the strain, to the rate of strain and, for muscle, to its activation. 

A classical answer is the Hill-type muscle model. Instead of following every small volume element, it lumps the tissue into a single force acting along the line of the muscle fibres. This force is built from a few phenomenological functions that reproduce experimental observations: the active force depends on the fibre length and on its velocity, the passive force grows when the muscle is stretched, and activation cannot change instantaneously (Figure 2).

A tendon is well described by a nonlinear elastic law: it is soft at first and becomes stiffer as it is stretched. Muscle is more complicated, because it can generate force actively.

In normalized form:

$$
F_M = F_{M0}\left[a\,f_L(\bar{L}_M)\,f_V(\bar{v}_M) + f_{PE}(\bar{L}_M)\right]
$$

where:

- \\( F_{M0} \\) is the maximum isometric force of the muscle
- \\( a \\) is the activation level, between 0 and 1
- \\( f_L \\) is the force–length relationship of the contractile element, with a maximum at the optimal fibre length
- \\( f_V \\) is the force–velocity relationship, which reduces the force when the muscle shortens and increases it when the muscle is stretched
- \\( f_{PE} \\) is the passive force of the parallel elastic element, which does not depend on activation
- \\( \bar{L}_M \\) and \\( \bar{v}_M \\) are the fibre length and velocity, normalized by the optimal length

<figure>
  <img src="{{ '/assets/img/hill_muscle_isometric.gif' | relative_url }}"
       alt="Figure 2. Hill muscle">
  <figcaption>
    <strong>Figure 2.</strong> Isometric contraction of a Hill-type muscle-tendon unit: as activation rises, the fibre shortens slightly and stretches the tendon, which transmits the force.
  </figcaption>
</figure>

The muscle is connected in series with an elastic tendon, so that the force transmitted to the skeleton is \\( F_T = F_M \cos\alpha \\), where \\( \alpha \\) is the pennation angle. Multiplying this force by the moment arm \\( r \\) of the muscle about the joint gives the torque it produces, \\( \tau = r\,F_T \\). This is the torque \\( \tau \\) that appears in the equation of motion of the inverted pendulum.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-7508630837578903"
     crossorigin="anonymous"></script>
<ins class="adsbygoogle"
     style="display:block; text-align:center;"
     data-ad-layout="in-article"
     data-ad-format="fluid"
     data-ad-client="ca-pub-7508630837578903"
     data-ad-slot="8175170690"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

#### Sources and references
<a href="https://bmclab.github.io/BMC/"
   target="_blank"
   rel="noopener noreferrer">
   GitHub - BMC Lab
</a> - Notes on Scientific Computing for Biomechanics and Motor Control
Figure 1 - AI generated using Claude (Anthropic) for dopamine-chamber.github.io
Figure 2 - generated via Python using BMC Notebook
