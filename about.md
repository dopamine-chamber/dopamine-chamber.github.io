---
layout: page
title: About
permalink: /about/
description: "About The Handstand Dilemma: a handstand practitioner's project where personal experience meets science communication."
---

<style>
  .liner { display: flex; align-items: center; gap: 1.5rem; margin: 1.5rem 0 2rem; }
  .liner-kicker { margin: 0; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.75rem; opacity: 0.65; }
  .liner-lead { margin: 0.25rem 0 0; font-size: 1.25rem; line-height: 1.3; font-weight: 600; }

  .vinyl {
    flex: none;
    width: 7.5rem;
    aspect-ratio: 1;
    border-radius: 50%;
    position: relative;
    background:
      radial-gradient(circle, transparent 0 30%, rgba(255,255,255,.06) 31% 32%, transparent 33% 100%),
      repeating-radial-gradient(circle, #111 0 2px, #1d1d1d 3px 4px);
    box-shadow: 0 0 0 2px rgba(128, 128, 128, 0.35);
    animation: spin 6s linear infinite;
  }
  .vinyl::before {
    content: "";
    position: absolute;
    inset: 33%;
    border-radius: 50%;
    background: radial-gradient(circle, #f5f0e6 0 5%, #c0392b 6% 100%);
  }
  .vinyl::after {
    content: "";
    position: absolute;
    inset: 0;
    border-radius: 50%;
    background: conic-gradient(from 20deg, transparent 0 20%, rgba(255,255,255,.12) 25%, transparent 30% 70%, rgba(255,255,255,.12) 75%, transparent 80%);
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .flow { margin: 1.5rem 0; }
  .flow figcaption { font-size: 0.85rem; opacity: 0.7; margin-top: 0.25rem; }

  .smallprint { border: 1px dashed rgba(128, 128, 128, 0.5); border-radius: 0.5rem; padding: 1rem 1.25rem; font-size: 0.9rem; margin: 2rem 0; }
  .smallprint p { margin: 0 0 0.6rem; }
  .smallprint p:last-child { margin-bottom: 0; }
  .smallprint-label { text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.7rem; opacity: 0.65; }

  .nowplaying { display: flex; align-items: center; gap: 0.75rem; margin-top: 2rem; padding-top: 1rem; border-top: 1px solid rgba(128, 128, 128, 0.35); }
  .nowplaying p { margin: 0; }
  .eq { display: inline-flex; align-items: flex-end; gap: 2px; height: 1.1rem; flex: none; }
  .eq span { width: 3px; height: 100%; background: #c0392b; transform-origin: bottom; animation: eq 1s ease-in-out infinite; }
  .eq span:nth-child(2) { animation-delay: 0.2s; }
  .eq span:nth-child(3) { animation-delay: 0.4s; }
  @keyframes eq { 0%, 100% { transform: scaleY(0.3); } 50% { transform: scaleY(1); } }

  @media (prefers-reduced-motion: reduce) {
    .vinyl, .eq span { animation: none; }
  }
</style>

<div class="liner">
  <div class="vinyl" aria-hidden="true"></div>
  <div>
    <p class="liner-kicker">Liner notes</p>
    <p class="liner-lead">This project holds what I’ve understood about handstands.</p>
  </div>
</div>

<p>I’ve been practicing handstands for about six years, and in that time I’ve come to realize how good it feels to channel my thinking into something so all-consuming. The Handstand Dilemma was born because my practice had grown too intricate for these thoughts to stay inside my head. I wanted to share them and build something out of them.</p>

<p>I’m a ’90s kid: blogging is my love language, and writing is one of the few things I’ve always been good at. Surprisingly, I’m a terribly introverted person, and sharing so much with strangers online is something I’ve always found almost therapeutic. With this project I wanted many parts of myself to meet: the kid who spends hours writing for her blog, the practitioner, the nerd, the need to have answers and to put things in order. This project holds what I’ve understood about handstands.</p>

<p>The editorial flow is a reorganization of my stream of consciousness, whose complexity grows in step with the time I spend practicing. Each topic is explored based on what the scientific literature and reliable sources tell us about handstand practice, so that personal experience and science communication can come together.</p>

<figure class="flow">
  <svg viewBox="0 0 420 170" role="img" aria-label="Schematic curve: the complexity of the writing grows as practice time increases" style="width:100%;max-width:26rem;height:auto">
    <line x1="30" y1="140" x2="400" y2="140" stroke="currentColor" stroke-opacity=".5"/>
    <line x1="30" y1="140" x2="30" y2="15" stroke="currentColor" stroke-opacity=".5"/>
    <path d="M30 135 C 140 132, 220 120, 280 80 S 360 28, 395 18" fill="none" stroke="#c0392b" stroke-width="3" stroke-linecap="round"/>
    <circle cx="395" cy="18" r="4" fill="#c0392b"/>
    <text x="38" y="26" font-size="11" fill="currentColor" opacity=".7">complexity</text>
    <text x="400" y="158" text-anchor="end" font-size="11" fill="currentColor" opacity=".7">time spent practicing</text>
  </svg>
  <figcaption>The editorial flow, roughly. Not to scale.</figcaption>
</figure>

<div class="smallprint">
  <p class="smallprint-label">Small print</p>
  <p>Therefore, the content published on this site is created in good faith and for informational purposes only, with all original sources duly cited within the articles. Every effort is made to respect third-party intellectual property rights. If you believe any content infringes upon your copyright, please contact me for immediate review and removal. Please see the privacy policy page for my contact details.</p>
  <p>All rights are reserved. Content may not be reproduced or redistributed without prior written consent.</p>
</div>

<div class="nowplaying">
  <div class="eq" aria-hidden="true"><span></span><span></span><span></span></div>
  <p><strong>Now playing.</strong> The page URL is a tribute to the latest Fontaines D.C. album.</p>
</div>
