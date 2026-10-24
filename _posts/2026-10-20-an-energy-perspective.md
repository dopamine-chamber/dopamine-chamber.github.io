---
layout: post
title: "An energy perspective"
date: 2026-10-20 12:00:00 +0200
---

Models help us understand the mechanics of a handstand, but how should the body adjust its position to maintain balance? To effectively restore equilibrium, adjustments must be applied in the right direction, with the appropriate magnitude, and at the right time. Mechanics can tell us which joint torques are needed, but not how to produce them: that takes training in strength, mobility and coordination. We set this aside for now and return to a simplified model in which the body behaves as a single-segment inverted pendulum pivoting about the wrists.

## Energy conservation in SIP

We consider motion in the sagittal plane, where main handstand sway occur. We have also seen that $$ddot{\theta}$$ as the notation used to represent a second derivative. Therefore, $$ddot{\theta}$$ corresponds to the second derivative of the angular position, that is, the angular acceleration ($$\omega$$). Throughout this article, we assume that positive angles represent a tilt to the right.

Recalling the rotational equation of motion:

$$I\ddot{\theta} = mgh\sin\theta + \tau$$

For small deviations ($$\theta \ll 1$$), we use $$\sin\theta \approx \theta$$, which gives:

$$I\ddot{\theta} \approx mgh\,\theta + \tau$$

If the body tilts to the right ($$\theta > 0$$), a negative torque is required to counteract the fall. However, simply pushing against the direction of the fall is not always sufficient: the effectiveness of a correction depends on its magnitude and timing, as well as the body’s angular velocity.

To quantify how torque transfers energy into rotational motion, we consider mechanical power ($$P$$). For a torque acting around a single axis:

$$
P = \tau\,\omega
$$

where $$\omega = \dot{\theta}$$ is the angular velocity.

Multiplying the full (nonlinear) equation of motion by $$\omega$$ gives

$$
I\ddot{\theta}\,\omega = mgh\sin\theta\,\omega + \tau\omega
$$

The left-hand side represents the rate of change of rotational kinetic energy $$E_k = \frac{1}{2}I\omega^2$$ (assuming $$I$$ is constant):

$$
\frac{dE_k}{dt} = I\omega\dot{\omega} = I\ddot{\theta}\,\omega
$$

The gravitational term is the power of gravity, which equals minus the rate of change of potential energy. We take the handstand position ($$\theta = 0$$) as the reference level, so that:

$$
E_p = m g h\,(\cos\theta - 1)
$$

Note: $$E_p \le 0$$, and that $$\theta = 0$$ is a maximum of $$E_p$$: the upright position is an unstable equilibrium.

<figure>
  <img src="img/fig1_undamped.gif" alt="Inverted pendulum with PD control and no damping oscillating about the vertical, with E_c constant">
  <figcaption>Figure 5b. The same controller without damping ($k_p > mgh$, $k_d = 0$). The restoring torque keeps the body from falling, but nothing dissipates energy: $dE_c/dt = 0$, so $E_c$ stays constant and the body oscillates about the vertical indefinitely. The equilibrium is stable but not asymptotically stable.</figcaption>
</figure>

Differentiating $E_p$ with respect to time, with $\omega = \dot\theta$:

$$
\frac{dE_p}{dt} = -\,m g h \,\sin\theta \; \omega
$$

Rearranging the power balance:

$$
\frac{dE_k}{dt} = -\frac{dE_p}{dt} + \tau\omega \implies \frac{d}{dt}(E_k + E_p) = \tau\omega
$$

Defining the total mechanical energy as 

$$E = E_k + E_p$$

wwe obtain the energy rate equation:

$$
\frac{dE}{dt} = \tau\omega
$$

This is the work–energy theorem applied to the pendulum: the rate of change of total mechanical energy equals the power delivered by the control torque. When the body tilts away from the vertical, gravitational potential energy decreases and, if $$\tau = 0$$, kinetic energy increases by exactly the same amount. Without a control torque the total energy is conserved ($$\frac{dE}{dt} = 0$$).

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
  <img src="img/fig2_damped.gif" alt="Inverted pendulum with PD control and damping returning to the vertical, with E and E_c tending to zero">
  <figcaption>Figure 5a. Inverted pendulum with PD control and damping ($k_p > mgh$, $k_d > 0$). The body returns to the vertical (left). The mechanical energy $E$ rises and falls as the torque alternately adds and removes energy ($dE/dt = \tau\omega$), while $E_c$ decreases monotonically ($dE_c/dt = -k_d\omega^2 \le 0$). Both tend to zero, the energy of the upright equilibrium.</figcaption>
</figure>

The two conditions can also be read directly from the energy equation. Add the energy stored in the "control spring" to the mechanical energy:

$$
E_c = \tfrac{1}{2} I \omega^2 + m g h\,(\cos\theta - 1) + \tfrac{1}{2} k_p \theta^2
$$

Using $dE/dt = \tau\,\omega$ and the PD law, one finds

$$
\frac{dE_c}{dt} = -k_d\,\omega^2 \le 0
$$

The derivative term continuously removes energy. Near the vertical,

$$
E_c \approx \tfrac{1}{2} I \omega^2 + \tfrac{1}{2}\,(k_p - m g h)\,\theta^2,
$$

which is positive definite exactly when $k_p > m g h$. Together these facts show that the system settles at the upright position.

Note: Without delay, any $$k_p > m g h$$ and $$k_d > 0$$ would be stable, however large. In reality the sensorimotor loop is slow: delays of 160 to 240 ms have been estimated in gymnasts. With a delay, the stable region in the plane of gains is bounded, so gains that are too high also destabilize the system. This is where over-correcting causes sustained oscillations, and why a well-tuned balance needs both enough stiffness and not too much.

However, the torque at the wrists is limited by the size of the contact area under the hands, so large perturbations cannot always be recovered. Moreover, shoulders and hips also contribute to balance control, and we will see a more accurate model to capture how other joints contribute to the balance.

#### Source and references
- [Loughborough University Repository](https://repository.lboro.ac.uk/articles/journal_contribution/Control_strategy_for_a_hand_balance/9630269?file=17279426) - Control strategy for a hand balance
- [Royal Society Open Science](https://royalsocietypublishing.org/rsos/article/4/7/161018/93310/Balance-control-strategies-during-perturbed-and) - Balance control strategies during perturbed and unperturbed balance in standing and handstand
- [Philosophical Transactions of the Royal Society A](https://royalsocietypublishing.org/rsta/article-abstract/367/1891/1195/17515/Delay-effects-in-the-human-sensory-system-during?redirectedFrom=fulltext) - Delay effects in the human sensory system during balancing
Figure 1, Figure 2 - Generated via Python
