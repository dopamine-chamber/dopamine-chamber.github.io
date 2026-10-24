---
layout: post
title: "The multi-segment model and joint strategies"
date: 2026-10-22
published: false
---

Now that we know reality is more complicated, we can accept that, under certain conditions, we don’t need such a sophisticated model to understand what happens. 
When we talk about straight handstands, we can consider three main segments, since the legs remain straight (Figure 5).
This configuration can be modeled by a triple inverted pendulum, a model widely used in robotics to describe the double-support balance of humanoid robots. 
We can use this model by considering that our pivots are the wrists and not the ankles; the segment proportions will change (Figure 6).


<div class="figure-row">
  <figure>
    <img src="{{ '/assets/img/handstand_three_segment_model.png' | relative_url }}"
         alt="Handstand three segment model">
    <figcaption>Figure 5. Three segment model.</figcaption>
  </figure>

  <figure>
    <img src="{{ '/assets/img/triple_inverted_pendulum_model.png' | relative_url }}"
         alt="Triple inverted pendulum model">
    <figcaption>Figure 6. Triple inverted pendulum model.</figcaption>
  </figure>
</div>


In an ideal straight handstand, we model the body as a simple inverted pendulum pivoting at the wrists. 
In reality, all bodies rely on a combination of wrist, shoulder, and hip strategies to manage perturbations. 
However, expert athletes are far more effective at constraining corrections to the wrists alone, as their training enables them to maintain proper alignment and body tightness under load.
