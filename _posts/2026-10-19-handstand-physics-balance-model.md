---
layout: post
title: "Handstand balance: modelling the problem"
image:
  path: /assets/img/og/handstand-physics-balance-model.png
  width: 1200
  height: 630
  alt: "Single rigid-body model of a handstand, seen from the sagittal plane"
description: "Beneath the apparent absence of motion, handstands are far from stationary: we start to explore the handstand balance model that explains why holding a handstand is hard."
author: Benedetta Giglio
date: 2026-10-19
last_modified_at: 2026-11-01
series_order: 1
---

There is a simple physical truth behind the ability to hold a handstand: the constant, *inevitable* pull of gravity. In fact, beneath the apparent absence of motion, a vibrant orchestra of variables contribute to the balance. To attempt to barely understand them and how they play their role in the symphony, we need a model that captures the real situation. This will be the research that, starting from there, will take place here.

*A friendly disclaimer: I am not a professional hand balancer, and the aim of this project is neither to provide a method for practicing handstands nor to teach how to perform them. Its purpose is to observe the phenomenon and describe the underlying principles that make it possible. What follows is a summary of the conceptual rabbit hole I have been exploring so far.*

## Is the handstand a dilemma?

For a long time, my engineering background led me to think of handbalancing as a problem of mechanical equilibrium. And for years, practicing handstands felt remarkably similar to solving a physics problem. 

*Which muscles should I recruit for a given task? (Which variables compose this system?)*<br>
*Which is the most important? (Which is the key variable?)*<br>
*How can I engage the strongest and most natural kinetic chain without introducing compensations? (Which method is the most effective?)*

And yet, what people generally say about handstands sound similar to what my Physics I professor said on the first day of the course:
"Sorry if this first lecture may sound complicated. Physics has no beginner level. So it's going to be a complicated lecture."

Talking of handstands, it's undeniable that the human body is literally not designed to balance itself on hands, nor for holding handstands for that long. Being upside down is not exactly what we evolved for. Anyway, I'm still fascinated by its ability to reorganize and adapt, even when faced with such an unusual, functionally useless, mentally draining and frustrating task. 
But it's important to go across this journey with the right amount of self-denial.
And a bit of rage.

## Understanding models (understanding handstands?)

To understand how these beautiful things (these that happen on hands) happen, we need a **model** that can be grasped on the cognitive level. Therefore, over the years, my all-consuming side project has been refining this model to make it fit the handstand dilemma, and ultimately to find the perfect solution to the system. <br>
**And practicing handstands, of course**. 

*Editorial note: in this blog there will be a fair amount of maths. Although they're very elegant, my mind doesn't love formulas. But they help a lot to support and clarify what often exists only in our mind as a confused cloud. Maths can also be remarkably relaxing at times. I tend to be an anxious person, and when irrational fears creep into my mind, I like to keep them in check by using numbers to anchor myself in reality. Almost always, I find that the anxiety was only in my head, not in the facts.*
     
Let's then use maths to prove that handstands can be held, and also why they are so difficult. And for the scope, we will give a *little* definition of what a model is.

A model is a simplified formalization of a real phenomenon or problem, expressed in a language that can be analyzed and that retains only the relevant variables. The first step is therefore choosing the **level of abstraction**: we need to determine which variables are relevant. Then we have to represent them in a language that allows precise treatment (e.g. equations). On the other hand, models are valid *only within the domain they were built for*, and if reality departs from their assumptions, the model must be revised.

Therefore, if someone asked you: *“What is the best model for mathematically describing how to do a handstand?”*, the first answer would be: *“Which type of handstand?”*<br>
And even before that: *what actually is a handstand?* 

While we were able to give a clear, agreed-upon definition for the model, the same cannot be done for the handstand. Not only because there are many different handstand variations (even if this must be considered in the model, of course), but because it is hard to define the problem itself without relying on personal experience.
*Handbalancing is deeply experiential, not spelled out. And complexity is part of the game.*

Therefore, modelling something that is hard to describe in explicit terms is no walk in the park. 
Regarding the level of abstraction, actually, I have trouble leaving out irrelevant aspects. I have a mind that tends to dwell on everything, analyzing it for so long that the rest of the world starts to flow past behind it while I end up *down the rabbit hole*, carrying along everything I found on the way. In short, for me, it calls for an in-depth study.

Anyway, from now on, trying to model the problem will happen on the **three anatomical planes** onto which human movement can be projected: the frontal (or coronal) plane, the transverse (or horizontal) plane, and the sagittal (or median) plane (Figure 1).

<figure>
  <img src="/assets/img/planes_of_human_movement.png"
       alt="Frontal, sagittal, and transverse planes through a standing human figure">
  <figcaption>Figure 1. Anatomical body planes.</figcaption>
</figure>

*Armed with these colorful hopes*, we will analyse all the problems of the handstand and try to isolate them, study them one by one, and then combine them into a cocktail party that should be our handstand. We will use formulas, see with our own eyes the dependence on the parameters, and make some assumptions. And, as we know, answers will be valid only within the assumptions we chose. 

## A pinch of assumptions and a first model: the body is a stick

Let's start with a first extremely simplified model. First, we have to make our boring but necessary assumptions: don't worry, these are the most relevant and we will treat them as given in the next posts.

- First, we suppose that the handstand system is perfectly symmetrical, with two arms pushing with the same force and in the same direction.<br>
- We assume zero inclination in the frontal plane, and consider only the inclination that occurs in the sagittal plane when we push with both fingers and palms to adjust the balance.<br>
- We also assume that arms, shoulders, hips and legs work identically and do not generate twists. 
- We initially treat the human body as a **single rigid body**, so that we can describe its motion through the position of its **centre of mass**.<br>
- We see its motion from the sagittal plane, which divides the head (or brain) from the rest of the body into right and left sections (Figure 2):


<figure>
  <img src="{{ '/assets/img/single_segment_handstand_pendulum_model.png' | relative_url }}"
       alt="Handstand modelled as a single rigid segment pivoting about the wrists, with the centre of mass marked">
  <figcaption>Figure 2. The body modelled as a single element described by its center of mass.</figcaption>
</figure>

In this easy but not simple body configuration, the governing equation is Newton’s second law:

$$
\sum \mathbf{F} = m\mathbf{a}_{CM}
$$

When the centre of mass translates in the sagittal plane due to physiological handstand revocery swings, gravity will produce a moment about the wrists we can write this way: 

$$
\sum M_{O} = I_{O}\,\alpha = mgh+\tau
$$

When we hold a handstand, the net moment must be zero, meaning there are no accelerations and the moment generated by gravity is perfectly counteracted by the torque generated by the wrists:

$$
mgh+\tau = 0 \Rightarrow mgh = - \tau 
$$

In a real handstand, however, the body is never perfectly stationary and perpendicular to the floor. Small adjustments are performed at the hand level, which means the acceleration is not zero. In the next post, we will introduce dynamics and analyze the torques that keep the body (barely) upright.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-7508630837578903"
     crossorigin="anonymous"></script>
<ins class="adsbygoogle"
     style="display:block; text-align:center;"
     data-ad-layout="in-article"
     data-ad-format="fluid"
     data-ad-client="ca-pub-7508630837578903"
     data-ad-slot="5117550483"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>

This post is part of *[the handstand balance model](/series/).
[Next: a more accurate handstand balance model →](https://dopamine-chamber.github.io/2026/10/20/an-energy-perspective.html)* 

#### Sources and references

- Royal Society Open Science - [*Balance control strategies during perturbed and unperturbed balance in standing and handstand*](https://doi.org/10.1098/rsos.161018){:target="_blank" rel="noopener noreferrer"} ([open access](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5541526/){:target="_blank" rel="noopener noreferrer"})
- Medicine & Science in Sports & Exercise - [*Strategies for maintaining a handstand in the anterior-posterior direction*](https://pubmed.ncbi.nlm.nih.gov/11445766/){:target="_blank" rel="noopener noreferrer"}
- Loughborough repository - [*Control strategy for a hand balance*](https://repository.lboro.ac.uk/articles/journal_contribution/Control_strategy_for_a_hand_balance/9630269){:target="_blank" rel="noopener noreferrer"}
- Gait & Posture - [*Human balance and posture control during standing and walking*](https://doi.org/10.1016/0966-6362(96)82849-9){:target="_blank" rel="noopener noreferrer"}

- Figures 1, 2: AI-generated illustration created with Claude (Anthropic) for [dopamine-chamber.github.io](https://dopamine-chamber.github.io/){:target="_blank" rel="noopener noreferrer"}
