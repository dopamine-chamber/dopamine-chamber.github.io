---
layout: post
title: "2. An energy perspective"
date: 2026-10-20 12:00:00 +0200
---

To effectively restore equilibrium, adjustments must be applied in the right direction, with the appropriate magnitude, and at the right time. Models help us understand the mechanics of a handstand, and mechanics can tell us which joint torques are needed. But learning how to produce them is another discipline that includes training in strength, mobility and coordination. 

<details>
<summary>Toolbox</summary>

<div style="text-align: left;">
  
- Rigid body: an idealisation in which the distance between any two points of the body stays constant: the body does not deform and can only translate and rotate. In biomechanics, the human body is often represented as a rigid-body model.<br>
- Newton’s second law: the net force on a body equals its mass times its acceleration (ΣF = ma). Its rotational analogue is that the net moment equals the moment of inertia times the angular acceleration (ΣM = Iα).<br>
- Moment (of a force): the rotational effect of a force about a point. It is used interchangeably with torque in the post.<br>
- Angular velocity (ω): how fast the tilt angle changes over time [rad/s]. It is the time derivative of θ.<br>
- Angular acceleration (α): how fast the angular velocity changes over time [rad/s²].<br>
- Rotational dynamic equilibrium: the condition in which the net moment about the pivot is zero, so the angular acceleration is zero. The body is either still or rotating at constant speed.<br>
- Control torque (τ): the torque the athlete produces at the wrists to oppose gravity’s torque.<br
- Moment of inertia: a measure of a body’s resistance to changes in its rotation.<br>
- Centre of mass (CoM): the point where the whole mass of a body can be considered concentrated, and which moves like a single particle subject to the total external force.<br>
- Lever arm: the perpendicular distance between the line of action of a force and the axis of rotation.<br>
- Torque: the rotational effect of a force about an axis, equal to the force times its lever arm.<br
- Pivot: the fixed point about which the body rotates. In the model it is the wrists.
- Amplitude (θ₀): the maximum angle reached during the oscillation.<br>
- Angular frequency (ω₀): how fast the oscillation cycles [rad/s]. It is related to the period by T = 2π/ω₀.<br>
- Period (T): the time taken for one complete oscillation [s].<br>
- Hanging pendulum: a body free to rotate about a pivot, with its centre of mass below it. Gravity acts as a restoring torque, so the equilibrium is stable and, for small angles, the motion is harmonic.
  
</div>

</details>
<br>

## Introducing mechanical power

Let's go back to our SIP: we consider motion in the sagittal plane, where the main handstand sway occur. We have also seen that $$\dot{\theta}$$ as the notation used to represent a derivative. Therefore, $$\dot{\theta}$$ corresponds to the derivative of the angular position $$\theta$$, that is the angular velocity ($$\omega$$), and  $$\ddot{\theta}$$ corresponds to the derivative of the angular velocity $$\dot{\theta}$$, or the second derivative of the angular position $$\theta$$, that is the angular acceleration ($$\dot{\omega}).

Throughout this article, we assume that positive angles represent a tilt to the right.

*Note: as you noticed, this post contains a lot of maths, which may make the notation a bit heavy. If you want to skip the whole mathematical treatment, jump straight to the section “Conservation of mechanical energy in SIP”.*

Recalling the rotational equation of motion:

$$I\ddot{\theta} = mgh\sin\theta + \tau$$

For small deviations ($$\theta \ll 1$$), we use $$\sin\theta \approx \theta$$, which gives:

$$I\ddot{\theta} \approx mgh\,\theta + \tau$$

If the body tilts to the right ($$\theta > 0$$), a negative torque is required to counteract the fall. 

To quantify how torque transfers energy into rotational motion, we introduce **mechanical power** ($$P$$), expressed in **watt** (torque × angular velocity).

For a torque acting around a single axis:

$$
P = \tau\,\omega
$$

with $$\omega = \dot{\theta}$$ being the angular velocity.

Multiplying the full (nonlinear) equation of motion by $$\omega$$ turns every term into a power: 

$$
I\ddot{\theta}\,\omega = mgh\sin\theta\,\omega + \tau\omega
$$

Analyzing terms:

- The left-hand side represents the contribute due to rate of change of rotational kinetic energy $$E_k = \frac{1}{2}I\omega^2$$ (assuming $$I$$ is constant):

$$
\frac{dE_k}{dt} = I\omega\dot{\omega} = I\ddot{\theta}\,\omega
$$

- The gravitational term is the power of gravity. Gravity is a conservative force, so its torque can be written as minus the derivative of a potential energy $$E_p$$ with respect to the angle:

$$mgh\sin\theta = -\frac{dE_p}{d\theta}$$

Integrating gives:

$$
E_p = mgh\cos\theta + \text{const}
$$

The term $$mgh\cos\theta$$ is simply the weight times the height of the centre of mass above the wrists, $$h\cos\theta$$. Only changes in potential energy matter, so we are free to choose where it is zero: we take the handstand position ($$\theta = 0$$) as the reference level, so that

$$E_p = mgh\,(\cos\theta - 1)$$

By the chain rule, $$\frac{dE_p}{dt} = \frac{dE_p}{d\theta}\,

\omega = -mgh\sin\theta\,\omega$$, so the gravitational term in the power balance is exactly $$-\frac{dE_p}{dt}$$.

Note that $$\cos\theta \le 1$$, so $$E_p \le 0$$: any tilt lowers the centre of mass, and with it the potential energy.

In other words, $$\theta = 0$$ is a maximum of $$E_p$$, like a ball on top of a hill. Any small displacement releases potential energy, which turns into kinetic energy: the upright position is an unstable equilibrium. For small angles, $$E_p \approx -\tfrac{1}{2}mgh\,\theta^2$$, that is an upside-down parabola: this is the energy counterpart of the $$mgh\,\theta$$ term in the linearised equation, which pushes the body away from the vertical (Figure 1).

Differentiating $$E_p$$ with respect to time, with $$\omega = \dot\theta$$:

$$
\frac{dE_p}{dt} = -\,m g h \,\sin\theta \; \omega
$$

Rearranging the power balance:

$$
\frac{dE_k}{dt} = -\frac{dE_p}{dt} + \tau\omega \implies \frac{d}{dt}(E_k + E_p) = \tau\omega
$$

Defining the total mechanical energy as 

$$E = E_k + E_p$$

we obtain the energy rate equation:

$$
\frac{dE}{dt} = \tau\omega
$$

## Conservation of mechanical energy in SIP

Another way to see how the wrists must work against gravity is to think in terms of energy. In our single-segment model, the body has a **kinetic energy** (it is moving) and a **gravitational potential energy** (how high its centre of mass is). The upright position is the highest point: any tilt lowers the centre of mass, so gravity releases energy and the body speeds up as it falls, like a ball rolling off the top of a hill. Left alone, the total energy stays constant, and the body falls away from the vertical.

<figure>
  <img src="/assets/img/fig_hilltop.gif" alt="Inverted pendulum with no control torque falling away from the vertical while its kinetic energy grows and the total energy stays constant">
  <figcaption markdown="span">Figure 1. Conservation of energy for the inverted pendulum with no control torque ($$\tau = 0$$). The upright position is a maximum of $$E_p$$, so the body falls away from it: kinetic and potential energy are exchanged while their sum $$E$$ stays constant.</figcaption>
</figure>


The only thing that can change the total energy is the torque at the wrists, which adds or removes energy depending on whether it acts along or against the motion. Balancing is therefore not simply “pushing against the fall”: the wrists have to add or remove the right amount of energy at the right moments, until both the tilt and the velocity go to zero. This is why small, well-timed adjustments work better than large, abrupt ones.

We can describe this with a simple control rule: a torque that grows with the tilt (like a spring pulling the body back) and one that grows with the speed (like a damper absorbing the oscillations). The spring has to be stiffer than gravity’s pull, otherwise the body simply falls; without damping, it would swing around the vertical forever without settling. In real bodies, delays in the nervous system (160–240 ms in gymnasts) limit how strong the correction can be: too weak and we fall, too strong and we over-correct and oscillate. And the wrists can only produce a limited torque, bounded by the size of the contact area under the hands.

<figure>
  <img src="/assets/img/fig1_undamped.gif" alt="Inverted pendulum with PD control and no damping oscillating about the vertical, with E_c constant">
  <figcaption markdown="span">Figure 2. Energy conservation for single inverted pendulum with torque control.</figcaption>
</figure>

This is the work–energy theorem applied to the pendulum (Figure 2): the rate of change of total mechanical energy equals the power delivered by the control torque. When the body tilts away from the vertical, gravitational potential energy decreases and, if $$\tau = 0$$, kinetic energy increases by exactly the same amount. Without a control torque the total energy is conserved ($$\frac{dE}{dt} = 0$$).

With this choice of reference, the upright equilibrium has $$E=0$$. Balancing therefore means bringing E to zero while $$\omega$$ goes to zero as well, and the control torque is the only way to change E. Its role is not merely to oppose the fall, but to add or remove energy at the right moments. Balancing on one's hands is, in this sense, a matter of energy management through well-timed, calibrated adjustments rather than abrupt, large corrections.

## The damped oscillator

To illustrate this control mechanism, consider a linear Proportional-Derivative (PD) control law:

$$
\tau = -k_p\theta - k_d\dot{\theta}
$$

The term $$-k_p\theta$$ is a restoring torque proportional to the angular displacement, while $$-k_d\dot{\theta}$$ provides damping proportional to the angular velocity. Wrist torques of this form, linear in the displacement and velocity of the centre of mass, have been proposed as a model of the wrist strategy used by gymnasts.

Substituting this control law into the linearized equation of motion yields:

$$
I\ddot{\theta} + k_d\dot{\theta} + (k_p - mgh)\theta = 0
$$

To guarantee asymptotic stability around the vertical equilibrium ($$\theta = 0$$, $$\dot{\theta} = 0$$), the gains must satisfy two strict inequalities:

$$
k_d > 0 \qquad \text{and} \qquad k_p > mgh
$$

The condition $$k_p > mgh$$ means that the active stiffness produced by the muscles must exceed the destabilizing pull of gravity, while  $$k_d > 0$$ provides the dissipation that damps oscillations. The two conditions fail in different ways. If $$k_p < mgh$$, the body simply falls. If $$k_p > mgh$$ but $$k_d = 0$$, the body oscillates about the vertical without ever settling.

<figure>
  <img src="/assets/img/fig2_damped.gif" alt="Inverted pendulum with PD control and damping returning to the vertical, with E and E_c tending to zero">
  <figcaption markdown="span">Figure 3. Inverted pendulum with PD control and damping ($$k_p > mgh$$, $$k_d > 0$$). The body returns to the vertical (left). The mechanical energy $$E$$ rises and falls as the torque alternately adds and removes energy ($$dE/dt = \tau\omega$$), while $$E_c$$ decreases monotonically ($$dE_c/dt = -k_d\omega^2 \le 0$$). Both tend to zero, the energy of the upright equilibrium.</figcaption>
</figure>

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

Note: Without delay, any $$k_p > m g h$$ and $$k_d > 0$$ would be stable, however large. In reality the sensorimotor loop is slow: delays of 160 to 240 ms have been estimated in gymnasts. With a delay, the stable region in the plane of gains is bounded, so gains that are too high also destabilize the system. This is where over-correcting causes sustained oscillations, and why a well-tuned balance needs both enough stiffness and not too much.

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
