---
layout: post
title: "3. The damped oscillator: how good are your fingers?"
date: 2026-10-21 12:00:00 +0200
---

## The damped oscillator

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
Figure 1, Figure 2 - Generated via Python for dopamine-chamber.github.io
