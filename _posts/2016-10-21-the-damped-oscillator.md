---
layout: post
title: "3. The damped oscillator: how good are your fingers?"
date: 2026-10-21 12:00:00 +0200
---

In the [previous post](/2026/10/20/an-energy-perspective.html) we saw that, in our model, the wrists are the only way to change the energy of the body: without a control torque the upright position is the top of a hill, and the body simply falls. What we have not said yet is how the torque should be produced.


<details>
<summary>Toolbox</summary>

<div style="text-align: left;">

- Feedback control: a strategy in which the control torque is computed from the measured state of the system (here the tilt and its rate of change), so that errors are corrected as they appear.<br>
- PD control: Proportional-Derivative control, $$\tau = -k_p\theta - k_d\dot{\theta}$$. One term reacts to how far the body is from the vertical, the other to how fast it is moving.<br>
- Gains ($$k_p$$, $$k_d$$): the coefficients that set the strength of each term. They are the "tuning knobs" of the controller; in the body they correspond to how strongly and how quickly the wrists respond.<br>
- Restoring torque (active stiffness): the $$-k_p\theta$$ term, which pulls the body back towards the vertical like a spring. $$k_p$$ plays the role of a spring constant produced by the muscles.<br>
- Damping (dissipation): the $$-k_d\dot{\theta}$$ term, proportional to the angular velocity, which removes energy and stops the oscillations.
- Net stiffness ($$k_p - mgh$$): gravity acts on the inverted pendulum like a negative spring of stiffness $$mgh$$, so the stiffness that actually matters is the active one minus gravity's.<br>
- Damped oscillator: a system obeying $$I\ddot{\theta} + k_d\dot{\theta} + k\theta = 0$$, with $$k = k_p - mgh$$. Its natural frequency is $$\omega_n = \sqrt{k/I}$$ and its damping ratio is $$\zeta = k_d / (2\sqrt{Ik})$$. With $$\zeta = 0$$ it oscillates forever; with $$0 < \zeta < 1$$ it oscillates with decaying amplitude; with $$\zeta \ge 1$$ it returns without oscillating.<br>
- Linearisation: replacing the exact equations with their first-order version around an equilibrium, valid for small deviations (here $$\sin\theta \approx \theta$$).<br>
- Equilibrium and asymptotic stability: an equilibrium is a state where the system can stay at rest. It is asymptotically stable if, after a small disturbance, the system returns to it and stays there.<br>
- Positive definite function: a function that is positive everywhere except at the equilibrium, where it is zero. If an energy-like function of this kind never increases along the motion (a Lyapunov function), the equilibrium is stable.<br>
- Sensorimotor delay: the time between a disturbance and the muscular response, made up of sensing, neural processing and muscle activation. In handstands it has been estimated at 160–240 ms in a small sample of gymnasts.<br>
- Wrist strategy: balancing a handstand mainly by changing the torque at the wrists (fingers and palms), while shoulders and hips keep the body configuration fixed.<br>
- Contact area (centre of pressure): the torque at the wrists comes from shifting the point where the force is applied under the hands, so it cannot exceed what the size of the contact area allows.<br>
  
</div>

</details><br>


## The linear Proportional-Derivative (PD) control law

To illustrate this control mechanism, consider a linear Proportional-Derivative (PD) control law, a type of feedback control that combines proportional and derivative actions to regulate the behavior of a system:

$$
\tau = -k_p\theta - k_d\dot{\theta}
$$

The term $$-k_p\theta$$ is a restoring torque proportional to the angular displacement, while $$-k_d\dot{\theta}$$ provides damping proportional to the angular velocity.

Wrist torques of this form, linear in the displacement and velocity of the centre of mass, have been proposed as a model of the wrist strategy used by gymnasts.

Substituting this control law into the linearized equation of motion (valid for small angles) yields:

$$
I\ddot{\theta} + k_d\dot{\theta} + (k_p - mgh)\theta = 0
$$

To guarantee **asymptotic stability** (the ability of the system to return to equilibrium after a disturbance that in out model, remember, it's considered small) around the vertical equilibrium ($$\theta = 0$$, $$\dot{\theta} = 0$$), the gains must satisfy two conditions:

$$
k_d > 0 \qquad \text{and} \qquad k_p > mgh
$$

The condition $$k_p > mgh$$ means that the active stiffness produced by the muscles must exceed the destabilizing pull of gravity, while  $$k_d > 0$$ provides the dissipation that damps oscillations.

<figure>
  <img src="/assets/img/fig2_damped.gif" alt="Inverted pendulum with PD control and damping returning to the vertical, with E and E_c tending to zero">
  <figcaption markdown="span">Figure 3. Inverted pendulum with PD control and damping ($$k_p > mgh$$, $$k_d > 0$$). The body returns to the vertical (left). The mechanical energy $$E$$ rises and falls as the torque alternately adds and removes energy ($$dE/dt = \tau\omega$$), while $$E_c$$ decreases monotonically ($$dE_c/dt = -k_d\omega^2 \le 0$$). Both tend to zero, the energy of the upright equilibrium.</figcaption>
</figure>

Actually:
- If $$k_p < mgh$$, the body simply falls
- If $$k_p > mgh$$ but $$k_d = 0$$, the body oscillates about the vertical without ever settling.


The two conditions can also be read directly from the energy equation. Add the energy stored in the "control spring" to the mechanical energy:

$$
E_c = \tfrac{1}{2} I \omega^2 + m g h\,(\cos\theta - 1) + \tfrac{1}{2} k_p \theta^2
$$

Using $$dE/dt = \tau\,\omega$$ and the PD law, one finds

$$
\frac{dE_c}{dt} = -k_d\,\omega^2 \le 0
$$

The derivative term continuously removes energy. Near the vertical,

$$
E_c \approx \tfrac{1}{2} I \omega^2 + \tfrac{1}{2}\,(k_p - m g h)\,\theta^2,
$$

which is positive definite exactly when $$k_p > m g h$$. Together these facts show that the system settles at the upright position.

Note: Without delay, any $k_p > m g h$ and $k_d > 0$ would be stable, however large. In reality the sensorimotor loop is slow. In a study of four male gymnasts, Yeadon and Trewartha (2003) estimated delays of 160 to 240 ms by regressing the wrist torque against earlier values of the centre-of-mass position and velocity. These are statistical estimates from a small sample, not direct measurements, so they should be read as an order of magnitude, but they are consistent with long-latency reflexes. With a delay, the stable region in the plane of gains is bounded, so gains that are too high also destabilize the system. This is where over-correcting causes sustained oscillations, and why a well-tuned balance needs both enough stiffness and not too much.

With a delay, the stable region in the plane of gains is bounded, so gains that are too high also destabilize the system. This is where over-correcting causes sustained oscillations, and why a well-tuned balance needs both enough stiffness and not too much.

However, the torque at the wrists is limited by the size of the contact area under the hands, so large perturbations cannot always be recovered. Moreover, shoulders and hips also contribute to balance control, and we will see a more accurate model to capture how other joints contribute to the balance.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-7508630837578903"
     crossorigin="anonymous"></script>
<ins class="adsbygoogle"
     style="display:block; text-align:center;"
     data-ad-layout="in-article"
     data-ad-format="fluid"
     data-ad-client="ca-pub-7508630837578903"
     data-ad-slot="8199221420"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

#### Source and references
- [Loughborough University Repository](https://repository.lboro.ac.uk/articles/journal_contribution/Control_strategy_for_a_hand_balance/9630269?file=17279426) - Control strategy for a hand balance
- [Royal Society Open Science](https://royalsocietypublishing.org/rsos/article/4/7/161018/93310/Balance-control-strategies-during-perturbed-and) - Balance control strategies during perturbed and unperturbed balance in standing and handstand
- [Philosophical Transactions of the Royal Society A](https://royalsocietypublishing.org/rsta/article-abstract/367/1891/1195/17515/Delay-effects-in-the-human-sensory-system-during?redirectedFrom=fulltext) - Delay effects in the human sensory system during balancing<br>
Figure 1 - Generated via Python for dopamine-chamber.github.io
