---
layout: post
title: "2. An energy perspective: less is more?"
date: 2026-10-20 12:00:00 +0200
---

The intrinsic instability of the system can also be explained through the concept of energy. When we are in a handstand, we are intuitively in a state of unstable equilibrium: we are almost motionless, but because of the unfavorable configuration we occupy within the gravitational field, our potential energy is at its maximum.

<details>
<summary>Toolbox</summary>

<div style="text-align: left;">

- Dot notation: θ̇ and θ̈ are the first and second time derivatives of the tilt angle. θ̇ = ω is the angular velocity [rad/s]; θ̈ = α is the angular acceleration [rad/s²]<br>

- Small-angle approximation: for θ ≪ 1 rad, sin θ ≈ θ and cos θ ≈ 1 − θ²/2. It turns the nonlinear equations into linear ones<br>

- Mechanical power: the rate at which a force or torque transfers energy. For a torque about a fixed axis, P = τω [W]<br>

- Rotational kinetic energy: the energy of rotation, E_k = ½Iω²<br>

- Conservative force: a force whose work depends only on the start and end positions, so it can be described by a potential energy. Gravity is one<br>

- Gravitational potential energy and reference level: the energy stored by position. For the pendulum it is mg times the height of the CoM above the wrists, h cos θ. Only changes matter, so the zero can be chosen freely; here it is the upright position<br>

- Mechanical energy and work–energy theorem: E = E_k + E_p. Its rate of change equals the power of the non-conservative torques: dE/dt = τω
- 
Chain rule: if y depends on x and x on t, then dy/dt = (dy/dx)(dx/dt)<br>

- Unstable equilibrium: an equilibrium that a small disturbance makes the system leave. In the inverted pendulum it is a maximum of the potential energy<br>
  
</div>

</details>
<br>

## Introducing mechanical power

In the previous post we modelled our handstand like an inverted pendulum that want to mask as a hanging pendulum. The motion we want to recall is the simple harmonic motion, with our centre of mass oscillating periodically about its equilibrium position. (Figure 1).

Keep in mind that this behaviour is only possible because of **active control at the wrists**. Unlike a hanging pendulum, an inverted pendulum is not governed by simple harmonic motion and cannot remain stable without continuous corrective action.

<figure>
  <img src="/assets/img/fig1_undamped.gif" alt="Inverted pendulum with PD control and no damping oscillating about the vertical, with E_c constant">
  <figcaption markdown="span">Figure 1. Inverted pendulum with torque control.</figcaption>
</figure>

Conceptually, I have always liked to think of these adjustments in terms of energy, because the importance of giving the right angular impulse (torque times duration) is something you learn from experience. 

In fact $$\frac{dE}{dt} = \tau\omega$$, meaning the "power of the force" is the rate at which that force transfers energy to the system. The energy changes only through the work done by the wrists, so it is intuitive to aim at keeping it constant, but at the right value. In the following, we verify how maths supports our intuition.

*Editorial note: the following part contains a lot of maths, which may make the notation a bit heavy. If you want to skip the whole mathematical treatment and go directly to what interests you most, please jump straight to the section: “Conservation of mechanical energy in SIP”. The whole picture will not change.*

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

Since only changes in potential energy matter, we are free to choose where it is zero.

*We take the handstand position as the reference level* ($$\theta = 0$$), so that:

$$E_p = mgh\,(\cos\theta - 1)$$

By the chain rule:

$$
\frac{dE_p}{dt} = \frac{dE_p}{d\theta}\,\omega = -mgh\sin\theta\,\omega
$$

so the gravitational term in the power balance is exactly $$-\frac{dE_p}{dt}$$.

Note that $$\cos\theta \le 1$$ by definition, so $$E_p \le 0$$: any tilt lowers the centre of mass, and with it the potential energy.

In other words, $$\theta = 0$$ is a maximum of $$E_p$$, like a ball on top of a hill. 
*Any small displacement releases potential energy, which turns into kinetic energy*: the upright position is an unstable equilibrium. 

For small angles:

cos θ ≈ 1 − θ²/2     →     $$E_p \approx -\tfrac{1}{2}mgh\,\theta^2$$

A torque is the negative slope of the energy. 

Differentiating $$E_p$$ with respect to $$\theta$$, the gravitational torque is:

$$
-\frac{dE_p}{d\theta} = mgh\sin\theta \approx mgh\,\theta
$$

which is exactly the term $$mgh\,\theta$$ in the linearised equation of motion, $$I_O\ddot{\theta} \approx mgh\,\theta + \tau$$.

Its sign is positive: it pushes the body in the direction in which it is already tilted, and therefore away from the vertical. The upside-down parabola is the same information, read as energy instead of torque: the steeper the hill, the stronger the push away from the top. (Figure 1).

Differentiating $$E_p$$ with respect to time, with $$\omega = \dot\theta$$:

$$
\frac{dE_p}{dt} = -\,m g h \,\sin\theta \; \omega
$$

Rearranging the power balance:

$$
\frac{dE_k}{dt} = -\frac{dE_p}{dt} + \tau\omega \implies \frac{d}{dt}(E_k + E_p) = \tau\omega
$$

Defining the **total mechanical energy** as $$E = E_k + E_p$$

we obtain the energy rate equation:

$$
\frac{dE}{dt} = \tau\omega
$$

## Conservation of mechanical energy in SIP

One way to understand how the wrists must work against gravity is to think in terms of power and energy. In our single-segment model, the body has a kinetic energy (it is moving) and a gravitational potential energy (how high its centre of mass is), which give the total mechanical energy of the system:

$$E = E_k + E_p$$

The upright position is where the centre of mass is highest, and we take it as the zero of potential energy (that in our model is the maximum): any tilt lowers the centre of mass, so gravity releases energy and the body speeds up as it falls, like a ball rolling off the top of a hill. Left to itself, the total energy stays constant, and the body falls away from the vertical (Figure 2).
  
- With $$E < 0$$, a body moving towards the vertical runs out of energy, stops short and falls back.
  
- With $$E > 0$$, it overshoots and falls to the other side.

<figure>
  <img src="/assets/img/fig_hilltop.gif" alt="Inverted pendulum with no control torque falling away from the vertical while its kinetic energy grows and the total energy stays constant">
  <figcaption markdown="span">Figure 2. Conservation of energy for the inverted pendulum with no control torque ($$\tau = 0$$). The upright position is a maximum of $$E_p$$, so the body falls away from it: kinetic and potential energy are exchanged while their sum $$E$$ stays constant.</figcaption>
</figure>

This is why flailing in response to a loss of balance backfires: a large correction can push $$E$$ well above zero, and the body overshoots. A correction that is too small leaves $$E < 0$$, and the body falls back.

In an ideal world, once $$E = 0$$ with the body moving towards the vertical, the wrists would have nothing left to do: $$\frac{dE}{dt} = \tau\omega = 0$$, and the energy would stay constant at zero. 

In reality, noise, delays and small perturbations keep pushing $$E$$ away from zero, so the muscles never stop working. The energy stays close to zero, with the wrists adding or removing small amounts of it, depending on whether the torque acts along ($$\tau\omega > 0$$) or against ($$\tau\omega < 0$$) the motion.

Balancing is therefore not simply “pushing against the fall”: the wrists have to add or remove the right amount of energy at the right moments, until both the tilt and the velocity go to zero. This is why small, well-timed adjustments work better than large, abrupt ones.

We can describe this with a simple control rule: a torque that grows with the tilt (like a spring pulling the body back) and one that grows with the speed (like a damper absorbing the oscillations). The spring has to be stiffer than gravity’s pull, otherwise the body simply falls; without damping, it would swing around the vertical forever without settling. In real bodies, delays in the nervous system (160–240 ms in gymnasts) limit how strong the correction can be: too weak and we fall, too strong and we over-correct and oscillate. And the wrists can only produce a limited torque, bounded by the size of the contact area under the hands.

In the next post we will see in details which control rule is good to describe and model our wrist control, performed, in our body, by our **fingertips**.

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

[Next post →](https://dopamine-chamber.github.io/2026/10/21/the-damped-oscillator)

#### Source and references
- [Loughborough University Repository](https://repository.lboro.ac.uk/articles/journal_contribution/Control_strategy_for_a_hand_balance/9630269?file=17279426) - Control strategy for a hand balance
- [Royal Society Open Science](https://royalsocietypublishing.org/rsos/article/4/7/161018/93310/Balance-control-strategies-during-perturbed-and) - Balance control strategies during perturbed and unperturbed balance in standing and handstand
- [Philosophical Transactions of the Royal Society A](https://royalsocietypublishing.org/rsta/article-abstract/367/1891/1195/17515/Delay-effects-in-the-human-sensory-system-during?redirectedFrom=fulltext) - Delay effects in the human sensory system during balancing<br>
Figure 1, Figure 2 - Generated via Python for dopamine-chamber.github.io
