---
layout: page
title: About
permalink: /about/
description: "About Signals from noise: a handstand practitioner’s project on motor learning, where personal experience meets science communication."
---

<style>
  .liner { margin: 2rem 0; padding: 0.1rem 0 0.1rem 1rem; border-left: 2px solid #ff2bd6; }
  .liner-lead { margin: 0; font-size: 1.25rem; line-height: 1.3; font-weight: 600; }

  .signal { margin: 1.5rem 0 2rem; }
  .signal iframe {
    display: block;
    width: 100%;
    height: 320px;
    border: 1px solid rgba(25, 240, 255, 0.3);
    background: #04050a;
  }
  .signal figcaption, .flow figcaption { font-size: 0.85rem; opacity: 0.7; margin-top: 0.4rem; }

  .flow { margin: 1.5rem 0; }

  /* Separators: a rule above and below each block.
     Two blocks in a row share the rule between them instead of doubling it. */
  .nowplaying {
    margin: 2rem 0 0;
    padding: 1rem 0;
    border-top: 1px solid rgba(128, 128, 128, 0.35);
    border-bottom: 1px solid rgba(128, 128, 128, 0.35);
  }
  .nowplaying + .nowplaying { margin-top: 0; border-top: 0; }
  .nowplaying p { margin: 0 0 0.6rem; }
  .nowplaying p:last-child { margin-bottom: 0; }
</style>

<p>I’ve been practicing handstands for about six years, and in that time I’ve come to realize that practice doesn’t build ability: it improves the quality of your predictions. I became obsessed with this idea. Signals from noise was born because my practice had grown too intricate for these thoughts to stay inside my head.</p>

<div class="liner">
  <p class="liner-lead">Learning is controlled hallucination converging toward truth.</p>
</div>

<p>Every attempt starts as a guess. The nervous system predicts where the body is and what the hands should do about it, reality answers, and the distance between the two is the error. A system does not care whether you call an attempt a success or a failure: it only receives information and learns by updating its model of reality.</p>

<h2>When learning diverges</h2>

<p>Updating is not the same as improving. If a correction overshoots badly enough, it leaves a bigger mistake than the one it set out to fix. The next one overshoots that too, and the model drifts further from reality at every step, until it blows apart. In a handstand the trap is overcorrection: the wrists act on information that is already old, and <a href="{{ '/2026/10/25/handstand-balance-damped-oscillator.html' | relative_url }}">past a certain point, pushing harder makes the sway grow</a>.</p>

<figure class="signal">
  <iframe src="{{ '/assets/img/about/learning_diverges.html' | relative_url }}" title="Animation: a learning model that diverges and explodes" loading="lazy" scrolling="no"></iframe>
  <figcaption>Diverging. Cyan is reality, magenta is the model, amber is the error. Every update overshoots, the error grows and the model is lost. A toy model of learning, not a simulation of the nervous system.</figcaption>
</figure>

<h2>When learning converges</h2>

<p>Take smaller steps and the same process turns around. The path still zigzags, nothing is solved in one leap, and the last stretch is the longest. But each update leaves the model a little closer to the world it is trying to predict. That is the slow convergence in this site’s address.</p>

<figure class="signal">
  <iframe src="{{ '/assets/img/about/learning_converges.html' | relative_url }}" title="Animation: a learning model that slowly converges" loading="lazy" scrolling="no"></iframe>
  <figcaption>Converging. Same toy model, smaller step: it zigzags down the loss valley, then creeps toward the target. In this model the error shrinks when the rate stays below 2 and grows when it goes above.</figcaption>
</figure>

<div class="liner">
  <p class="liner-lead">No error signal. No adaptation. No learning.</p>
</div>

<h2>Where this comes from</h2>

<p>I’m a ’90s kid: blogging is my love language, and sharing so much with strangers online is something I’ve always found almost therapeutic. This project is where many parts of myself meet, and holds what I’ve understood about handstands.</p>

<p>The editorial flow is a reorganization of my stream of consciousness, and each topic is explored based on what the scientific literature and reliable sources tell us about handstand practice. You can follow it from the start in <a href="{{ '/blog/series/' | relative_url }}">The handstand logs</a>.</p>

<figure class="flow">
  <svg viewBox="0 0 420 170" role="img" aria-label="Schematic curve: the complexity of the writing grows as practice time increases" style="width:100%;max-width:26rem;height:auto">
    <line x1="30" y1="140" x2="400" y2="140" stroke="currentColor" stroke-opacity=".5"/>
    <line x1="30" y1="140" x2="30" y2="15" stroke="currentColor" stroke-opacity=".5"/>
    <path d="M30 135 C 140 132, 220 120, 280 80 S 360 28, 395 18" fill="none" stroke="#ff2bd6" stroke-width="3" stroke-linecap="round"/>
    <circle cx="395" cy="18" r="4" fill="#ff2bd6"/>
    <text x="38" y="26" font-size="11" fill="currentColor" opacity=".7">complexity</text>
    <text x="400" y="158" text-anchor="end" font-size="11" fill="currentColor" opacity=".7">time spent practicing</text>
  </svg>
  <figcaption>The editorial flow, roughly. Not to scale.</figcaption>
</figure>

<div class="nowplaying">
  <p>The content published on this site is created in good faith and for informational purposes only, with all original sources duly cited within the articles. Every effort is made to respect third-party intellectual property rights. If you believe any content infringes upon your copyright, please contact me for immediate review and removal. Please see the <a href="{{ '/privacy-policy/' | relative_url }}">privacy policy page</a> for my contact details.</p>
  <p>All rights are reserved. Content may not be reproduced or redistributed without prior written consent.</p>
</div>

<div class="nowplaying">
  <p>The project was born in the days when the latest Fontaines D.C. album, <em>Dopamine Chamber</em>, was being released, and their music helped me get into the flow and inspired and motivated me deeply to create.</p>
</div>
