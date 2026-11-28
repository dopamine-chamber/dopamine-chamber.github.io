---
layout: page
title: Newsletter
permalink: /newsletter/
description: "A newsletter from signals from noise is on its way: new posts on motor learning and the physics of balance, plus the occasional note. Join the list to hear when the channel opens."
---

<style>
  .newsletter, .newsletter p { text-align: left; }
  .newsletter a.btn, .newsletter a.btn:visited { display: inline-block; padding: 0.55rem 1.1rem; margin: 0.5rem 0; border-radius: 6px; background: #222222; color: #fff; text-decoration: none; }
  .newsletter a.btn:hover, .newsletter a.btn:focus { background: #3a3fd1; color: #fff; text-decoration: none; }

  /* ---------- Hero animation ---------- */
  .hero-anim { margin: 0 0 1.5rem; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 7; max-height: 60vh; border: 0; background: #04050a; border-radius: 8px; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 4 / 3; } }

  .liner { margin: 1.5rem 0 2rem; }
  .newsletter .liner p { text-align: center; }
  .liner-kicker { margin: 0; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.75rem; opacity: 0.65; }
  .liner-lead { margin: 0.25rem auto 0; max-width: 30rem; font-size: 1.25rem; line-height: 1.3; font-weight: 600; }

  .payload-label { margin: 1.5rem 0 0; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.75rem; opacity: 0.65; }
  .payload { list-style: none; counter-reset: packet; padding: 0; margin: 0.5rem 0 1.5rem; border-top: 1px solid rgba(128, 128, 128, 0.35); }
  .payload li { counter-increment: packet; display: flex; align-items: baseline; gap: 1rem; padding: 0.55rem 0; border-bottom: 1px dashed rgba(128, 128, 128, 0.35); }
  .payload li::before { content: counter(packet, decimal-leading-zero); font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; font-weight: 700; font-variant-numeric: tabular-nums; color: #3a3fd1; opacity: 0.8; }
  .payload small { margin-left: auto; opacity: 0.6; white-space: nowrap; }

  .steps { list-style: none; display: flex; padding: 0; margin: 1.5rem 0; }
  .steps li { flex: 1; position: relative; text-align: center; font-size: 0.8rem; padding-top: 1.4rem; opacity: 0.6; }
  .steps li::before { content: ""; position: absolute; top: 0; left: 50%; width: 0.8rem; height: 0.8rem; margin-left: -0.4rem; box-sizing: border-box; border-radius: 50%; border: 2px solid currentColor; }
  .steps li::after { content: ""; position: absolute; top: 0.35rem; left: calc(-50% + 0.4rem); width: calc(100% - 0.8rem); height: 2px; background: currentColor; opacity: 0.4; }
  .steps li:first-child::after { display: none; }
  .steps li.done { opacity: 1; }
  .steps li.done::before { background: currentColor; }
  .steps li.now { opacity: 1; font-weight: 700; color: #3a3fd1; }
  .steps li.now::before { background: #3a3fd1; animation: pulse 1.6s ease-in-out infinite; }
  @keyframes pulse { 0%, 100% { box-shadow: 0 0 0 0 rgba(58, 63, 209, .5); } 50% { box-shadow: 0 0 0 6px rgba(58, 63, 209, 0); } }

  .smallprint { border: 1px dashed rgba(128, 128, 128, 0.5); border-radius: 0.5rem; padding: 1rem 1.25rem; font-size: 0.9rem; margin: 2rem 0; }
  .smallprint-label { margin: 0 0 0.6rem; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.7rem; opacity: 0.65; }
  .smallprint p:last-child { margin-bottom: 0; }

  @media (prefers-reduced-motion: reduce) {
    .steps li.now::before { animation: none; }
  }
</style>

<div class="newsletter">

  <figure class="hero-anim">
    <iframe
      src="{{ '/assets/img/newsletter/signal_transmission.html' | relative_url }}"
      title="Animation of data packets travelling from a transmitter to a receiver across a noisy channel: corrupted packets are rejected and sent again until one arrives intact"
      loading="lazy"
      scrolling="no">
    </iframe>
  </figure>

  <div class="liner">
    <p class="liner-kicker">Channel opening soon</p>
    <p class="liner-lead">A newsletter on motor learning and the physics of balance is on its way.</p>
  </div>

  <p>New posts and the occasional note that doesn’t fit in an article, delivered straight to your inbox. Think of it as a low-bandwidth channel: the signal, without the noise, sent when there is something worth sending.</p>

  <p class="payload-label">Payload</p>
  <ol class="payload">
    <li>New posts on motor learning and the physics of balance <small>in your inbox</small></li>
    <li>Side notes that don’t fit in an article <small>every now and then</small></li>
  </ol>

  <p>Leave your email address and I’ll let you know when the channel opens.</p>

 <p style="text-align: center;">
    <a class="btn"
       href="https://docs.google.com/forms/d/e/1FAIpQLScUHUH19eT3a6SQB5pTEzOYSEjTDFkXbTV4GtIru3jY2EoDoA/viewform"
       target="_blank"
       rel="noopener">
        Join the list
    </a>
</p>

  <div class="smallprint">
    <p class="smallprint-label">Small print</p>
    <p>The form is hosted by Google Forms and opens in a new tab. I’ll use your email address only to tell you when the newsletter launches and to send it afterwards. I won’t share it with anyone, and you can ask me to delete it at any time. Details in the <a href="{{ '/privacy-policy/' | relative_url }}">privacy policy</a>. Prefer not to use the form? Write to <a href="mailto:info@slowconvergence.com">info@slowconvergence.com</a> with “Newsletter” in the subject.</p>
  </div>

</div>
