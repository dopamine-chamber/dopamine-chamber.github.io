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
