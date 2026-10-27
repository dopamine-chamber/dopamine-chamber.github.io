---
layout: post
title: "Do taller people struggle more with handstands?"
date: 2026-10-26
---

In my years of practice, one thing I have heard a lot is that, as a short girl, I must find it easier to balance in a handstand. And yes, but… it's a simplistic way of thinking about the phenomenon, and I'm not comfortable with assumptions that come without any evidence. Of course, if an experienced athlete says it, I trust them: it's empirical, and I don't necessarily need evidence. But, you know, I'm obsessed with handstands, so if there is more to it than this, I need to discover it. So let's introduce another important concept in this handstand-dismantling journey.

## The wrist strategy and the centre of pressure

In my previous post, we derived that the torque exerted at the wrist is the player that counteracts the fall:

$$|\tau| = m g h \sin\theta$$

and drew a first result: the magnitude of the torque depends on the tilt $$\theta$$ and on the height $$h$$ of the centre of mass, and therefore on the height of the performer. 

The ability to recover from falling is defined **wrist strategy** among several studies of the handstand itself, which have examined how balance is maintained and controlled in the anterior–posterior direction. These studies, condupted among experienced athletes, have shown that wrist strategy is the most commonly used to recover the balance when the centre of mass is swaying from its stability range. In the future posts, we will explore other strategies, but we will need to introduce different models: as like as happens in handstand trainings, we will go step by step along this journey.

There is another important concept that comes up when talking about upright stance: the **centre of pressure** (CoP), the point of application of the resultant ground reaction force acting on the plantar surface of the foot (or feet) during standing, walking or other activities. It is the weighted average of all the pressure exerted by the foot on the ground, and its trajectory over time is widely used to assess balance, postural control and gait.

The same idea can be applied to the handstand, with the hands taking the place of the feet.

## Let's complicate our model a bit

The body is a rigid stick of mass $$m$$ and length $$H$$ rotating about the wrist, with the centre of mass (CoM) at distance $$h$$ from the pivot. Let $$\theta$$ be the inclination from the vertical (positive towards the fingers), $$d = h\sin\theta$$ the horizontal position of the CoM relative to the wrist, and $$c$$ the position of the CoP under the hand, also relative to the wrist. The CoP can only lie within the hand footprint (Figure 1).

<iframe
src="{{ '/assets/interactive/handstand_model.html' | relative_url }}"
width="100%"
height="700"
style="border:none;">
</iframe>



<figure>
  <img src="/assets/img/handstand_center_of_pressure_model.png" alt="centre of mass vs centre of pressure">
  <figcaption markdown="span">Figure 1. Schematic centre of mass and centre of pressure.</figcaption>
</figure>

Taking moments about the wrist, with the wrist at ground level and neglecting the mass hand:

$$I\,\ddot\theta = m g\, d - N c, \qquad N = m(g + \ddot z), \qquad F_x = m\,\ddot x,$$

where:

$$I = m,(H^2/12 + h^2)$$<br>
$$z = h\cos\theta$$<br>
$$x = h\sin\theta$$

Eliminating $$N$$ gives the instantaneous angular acceleration (Appendix A):

$$\ddot\theta = \frac{m g (d - c) + m c\, h\cos\theta\ \omega^2}{I - m c\, d}, \qquad \omega = \dot\theta.$$

The loads on the wrists are the vertical force $$N$$, the shear force $$F_x$$ (positive towards the fingers, the direction in which the body accelerates), their resultant $$F$$, and the wrist moment $$M = N c$$, that is the moment of the ground reaction about the wrist. All values are reported per wrist, the total being shared equally between the two hands.

we set the parameters:

| Parameter | Value |
|:---|:---|
| Body mass $$m$$ | 70 kg (body weight 687 N, 343 N per wrist) |
| Wrist-to-CoM distance $$h$$ | 1.00 m |
| Body height (total length of our stick) $$H$$ | 1.75 m, so $$I = 87.9\ \text{kg m}^2$$ about the wrist |
| Hand lenght| 20 cm
| Hand footprint | 2 cm behind the wrist to 18 cm in front of it |

### Note on the model

The equations above are evaluated on a grid of CoP and CoM positions with $$\omega = 0$$, giving the instantaneous loads as functions of the two positions.

The CoP is commanded as

$$
c = d_{ref} + k_p(\theta - \theta_{ref}) + k_d\,\omega
$$

saturated to the hand footprint, with controllers $$k_p = 1.5$$ and $$k_d = 0.30\ \text{s}$$. 

This stands for the modulation of palm and finger pressure; the gains are illustrative and not identified from data. 
The equations of motion are integrated with a fourth-order Runge–Kutta scheme (time step 1 ms, 6 s). A trial is counted as a fall if $$|\theta|$$ exceeds 0.35 rad. Each trial starts at rest with an angular offset of 0.04 rad (2.3°, about 4 cm of CoM displacement) from the reference posture 

$$
\theta_{ref} = \arcsin(d_{ref}/l)
$$

for four reference CoM positions.

Regarding recoverable margins, for a given reference CoM, the largest initial angular offset from which balance is recovered, forwards and backwards, is found by bisection (14 iterations, time step 2 ms, 6 s). It is reported as the corresponding CoM displacement in centimetres.

<figure>
  <img src="/assets/img/com vs cop.gif" alt=" Animation of the model">
  <figcaption markdown="span">Figure 2. Animation of the model. A) CoM = CoP is moved towards the fingers. B) CoP is fixed and the CoM moves backwards. C) CoM is fixed and the CoP moves back under it.</figcaption>
</figure>

In static equilibrium the wrist is loaded by a moment, not by extra force

When the CoM is vertically above the CoP ($$d = c$$) the body does not accelerate: 

$$N = mg$$ and shear force $$F_x = 0$$ and $$M = \frac{m g}{2}\, c \approx 3.4\ \text{N·m per cm of } c.$$

A CoP at 9 cm gives 343 N and 30.9 N·m per wrist, and a CoP at the fingertips (18 cm) gives about 62 N·m. 

In the lower-right panel, the iso-lines of the moment are vertical: the wrist moment depends on the CoP only, and in equilibrium the CoP is wherever the CoM is.

<figure>
  <img src="/assets/img/maps_cop_com.png" alt="Loads per wrist as functions of CoP (horizontal axis) and CoM (vertical axis), both relative to the wrist">
  <figcaption markdown="span">Figure 3. Heat maps of the vertical force, shear force, resultant force and wrist moment as functions of CoP and CoM. Loads per wrist as functions of CoP (horizontal axis) and CoM (vertical axis), both relative to the wrist. Dashed line: CoM = CoP. Dotted lines: hand edges. White square: region where equilibrium is feasible, with CoM and CoP both inside the hand.</figcaption>
</figure>

Away from equilibrium, shear force scales with the CoM–CoP offset. The iso-lines of $$F_x$$ in Figure 3 are parallel to the CoM = CoP diagonal: the shear force depends on the offset $$d - c$$ only. It is zero on the diagonal, positive when the CoM is ahead of the CoP (the body tips towards the fingers) and negative when it is behind. Near equilibrium it is about 2.7 N per centimetre of offset per wrist: an offset of 5 cm gives $$F_x = 13.7$$ N and $$\ddot\theta = 0.39\ \text{rad/s}^2$$, and an offset of 10 cm gives 27 N.

The vertical force is much less sensitive. Inside the feasible region $$N$$ stays between 334 and 346 N per wrist, within about 3 % of the static value, so the magnitude of the force on the wrist is a poor descriptor of wrist loading in this model. Over the same region the largest ratio 

$$
|F_x| / N
$$ 

is 0.16, reached at the corners where the offset is 20 cm. These are instantaneous values at $$\omega = 0$$; 
they indicate how much friction the hand would need to avoid slipping, not the loads during a real wobble.

3.3 Feasible region and correction margin

The white square in Figure 3 marks where equilibrium can exist at all. It also defines the correction margin: to stop a forward drift the CoP must be moved forwards of the CoM (pressing with the fingers), and to stop a backward drift it must be moved backwards (pressing with the heel of the hand). The hand offers only 2 cm of room behind the wrist and 18 cm in front of it.

Table 1 gives the largest CoM displacement from which balance is recovered, starting from rest, to within the numerical resolution of the bisection (about 0.1 cm).

Table 1. Recoverable CoM displacement and wrist moment for four reference CoM positions.

Reference CoM	Max recoverable displacement, forwards	Max recoverable displacement, backwards	Wrist moment at the reference

| Reference CoM | Max recoverable displacement, forwards | Max recoverable displacement, backwards | Wrist moment at the reference |
| :--- | :--- | :--- | :--- |
| 3 cm | 15.0 cm | 5.0 cm | 10.3 N·m |
| 8 cm (mid-hand) | 10.0 cm | 10.0 cm | 27.5 N·m |
| 9 cm | 9.0 cm | 11.0 cm | 30.9 N·m |
| 15 cm | 3.0 cm | 17.0 cm | 51.5 N·m |

In every case the forward margin equals the distance from the reference CoM to the fingertip edge (18 cm) and the backward margin equals the distance to the heel edge (−2 cm). In the cases tested, balance from rest is recoverable exactly as long as the CoM can be brought back within the hand footprint. The two margins are equal at mid-hand (8 cm), where the wrist moment is 27.5 N·m per wrist. Balancing closer to the wrist lowers the moment but leaves little room to correct backwards; balancing closer to the fingers raises the moment and leaves little room to correct forwards.

Three results stand out in Figure 4.

<figure>
  <img src="/assets/img/active_balance_simulation.png" alt="Active balance after an initial perturbation of 2.3°">
  <figcaption markdown="span">Figure 4. Active balance with a saturated CoP controller after an initial perturbation of 2.3°, for four reference CoM positions (1, 6, 10 and 15 cm). Grey band: hand footprint.</figcaption>
</figure>

Reference positions of 1, 6 and 10 cm are recovered, and the transients of $$F_x$$ and $$N$$ are almost identical in the three cases (shear stays below about 6 N per wrist). The reference position only shifts the baseline of the wrist moment, which settles at about 3.4 N·m per centimetre of reference CoM (roughly 3.5, 19.5 and 35.5 N·m).
The 15 cm case falls after 1.3 s. The correction requires a CoP of about 21 cm, beyond the 18 cm fingertip edge, so the controller saturates and cannot restore the balance.
Failure is a loss of control, not a force overload. Forces and moments stay modest in every recovered case; the limiting factor is whether the required CoP lies inside the hand. After the fall begins the plotted forces have no physical meaning, because the model assumes a flat hand and stops being valid.



## case 2:

<figure>
  <img src="/assets/img/com vs cop_short.gif" alt=" Animation of the model">
  <figcaption markdown="span">Figure 5. Animation of the model. A) CoM = CoP is moved towards the fingers. B) CoP is fixed and the CoM moves backwards. C) CoM is fixed and the CoP moves back under it.</figcaption>
</figure>

## Discussion

Within the assumptions of the model, two quantities answer two different questions. The CoP (equivalently the CoM, in equilibrium) sets how much the wrist is loaded through the moment $$M$$. The distance of the CoM from the edges of the hand sets how much disturbance can be corrected by changes of pressure alone. The balance position that minimises the moment is not the one that maximises the margin, and the margin is symmetric only at mid-hand.

Comparing the baseline model ($$70\text{ kg}$, $1.00\text{ m}$$) with the short model ($$50\text{ kg}$, $0.85\text{ m}$$) highlights how anthropometric scaling impacts performance: taller and heavier performers experience substantially larger wrist moments (up to $$>60\text{ N}\cdot\text{m}$$ per wrist vs $$\sim 40\text{ N}\cdot\text{m}$$ in shorter individuals) for the same relative CoP positions.   

While shorter performers benefit from reduced moments and lower rotational inertia, their smaller physical hand size limits the total absolute range of CoP modulation (saturating at $$\sim 13\text{ cm}$$ compared to $$\sim 18\text{ cm}$$). As a result, the absolute spatial tolerance for CoM displacement is scaled down.

For any performer, tall or short, the model suggests a necessary compromise between wrist loading and robustness rather than a single ideal posture.

## How good is the model?

While the model clearly indicates that taller individuals face a disadvantage due to higher moments of inertia ($$I \propto h^2$$) and greater joint torques, taller athletes often possess greater total muscle mass, which may partially compensate for the increased wrist torque requirements. In fact, the moment $$N c$$ is the moment of the ground reaction about the wrist, not a measured muscle or joint torque. However, the simulation assumes a fixed hand footprint saturation without accounting for dynamic finger stiffness variations or shoulder-width base changes. The wrist is at ground level, the hand mass is neglected, the hand stays flat. Furthermore, the body is modeled as a single inverted pendulum with one degree of freedom, ignoring multi-joint active corrections at the shoulders, hips, and knees. In the next post we will see a much better model to take other joints (and other strategies) into account.

Ultimately, the model is a model. Parameters (mass, distance $$h$$, stick lenght, hand footprint and controller gains) were plausible, but not measured.
Controls are idealised: there is no sensory delay, no noise and no actuator dynamics; the CoP responds instantly to the command within its limits. There is no validation: the model has not been compared with force-plate or kinematic data. The recoverable-margin simulations evaluate initial displacement from rest. They do not account for dynamic perturbations with initial angular velocity, which significantly narrow the recoverable envelope in practice.In conclusion, while the model mathematically confirms that taller individuals face higher torque demands and greater physical control challenges, empirical measurement of human performers is required to determine how real control strategies adapt to these biomechanical trade-offs.

Anyway, the result that the force on the wrist barely changes while the moment changes substantially also has a methodological consequence: studies that report only the force or the pressure under the hands would miss most of what changes with posture in this model, and the moment, which depends on where the load is applied, is the more informative quantity.

## Conclusions
In a single-pendulum model of the handstand, the force at each wrist stays close to half of body weight; posture changes the wrist moment (by about 3.4 N·m per centimetre of CoP) rather than the force.
The shear force depends only on the CoM–CoP offset (about 2.7 N per centimetre per wrist) and is small compared with the vertical force.
Balance from rest is recoverable as long as the CoM can be brought back within the hand footprint, so the choice of balance position trades wrist moment against correction margin; the margins are equal at mid-hand.
The conclusions are model-based and need experimental validation before being applied to real performers.



#### Source and references

<a href="https://www.circoteca.cl/wp-content/uploads/2019/08/Strategies-for-maintaining-a-handstand-in-the-anterior-posterior-direction-Revista-Ingles-DAVID-G.-KERWIN-GRANT-TREWARTHA-2001.pdf" target="_blank" rel="noopener noreferrer">
    University of Bath
</a> - Strategies for Maintaining a Handstand in the Anterior-Posterior Direction<br>
<a href="[[https://www.circoteca.cl/wp-content/uploads/2019/08/Strategies-for-maintaining-a-handstand-in-the-anterior-posterior-direction-Revista-Ingles-DAVID-G.-KERWIN-GRANT-TREWARTHA-2001.pdf" target="_blank" rel="noopener noreferrer](https://researchportal.bath.ac.uk/en/publications/control-strategy-for-a-hand-balance/)](https://pdfs.semanticscholar.org/b379/f56f1e52bd017e071ae18fde94f536c2a6d3.pdf)">
   Loughborough University
</a> - Control strategy for a hand balance


