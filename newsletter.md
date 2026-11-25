---
layout: page
title: Newsletter
permalink: /newsletter/
description: A newsletter on the physics of handstand balance is on its way. Join the list if you'd like to hear about it.
---

<style>
  .newsletter, .newsletter p { text-align: left; }
  .newsletter a.btn, .newsletter a.btn:visited { display: inline-block; padding: 0.55rem 1.1rem; margin: 0.5rem 0; border-radius: 6px; background: #222; color: #fff; text-decoration: none; }
  .newsletter a.btn:hover { opacity: 0.85; text-decoration: none; }

  .liner { margin: 1.5rem 0 2rem; }
  .newsletter .liner p { text-align: center; }
  .liner-kicker { margin: 0; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.75rem; opacity: 0.65; }
  .liner-lead { margin: 0.25rem auto 0; max-width: 30rem; font-size: 1.25rem; line-height: 1.3; font-weight: 600; }

  .vinyl {
    position: relative;
    width: 9rem;
    aspect-ratio: 1;
    margin: 0 auto 1.25rem;
    border-radius: 50%;
    background:
      radial-gradient(circle, transparent 0 30%, rgba(255,255,255,.06) 31% 32%, transparent 33% 100%),
      repeating-radial-gradient(circle, #111 0 2px, #1d1d1d 3px 4px);
    box-shadow: 0 0 0 2px rgba(128, 128, 128, 0.35);
    animation: spin 6s linear infinite;
  }
  .vinyl::before { content: ""; position: absolute; inset: 33%; border-radius: 50%; background: radial-gradient(circle, #f5f0e6 0 5%, #c0392b 6% 100%); }
  .vinyl::after { content: ""; position: absolute; inset: 0; border-radius: 50%; background: conic-gradient(from 20deg, transparent 0 20%, rgba(255,255,255,.12) 25%, transparent 30% 70%, rgba(255,255,255,.12) 75%, transparent 80%); }
  @keyframes spin { to { transform: rotate(360deg); } }

  .tracklist-label { margin: 1.5rem 0 0; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.75rem; opacity: 0.65; }
  .tracklist { list-style: none; counter-reset: track; padding: 0; margin: 0.5rem 0 1.5rem; border-top: 1px solid rgba(128, 128, 128, 0.35); }
  .tracklist li { counter-increment: track; display: flex; align-items: baseline; gap: 1rem; padding: 0.55rem 0; border-bottom: 1px dashed rgba(128, 128, 128, 0.35); }
  .tracklist li::before { content: counter(track, decimal-leading-zero); font-weight: 700; font-variant-numeric: tabular-nums; opacity: 0.55; }
  .tracklist small { margin-left: auto; opacity: 0.6; white-space: nowrap; }

  .steps { list-style: none; display: flex; padding: 0; margin: 1.5rem 0; }
  .steps li { flex: 1; position: relative; text-align: center; font-size: 0.8rem; padding-top: 1.4rem; opacity: 0.6; }
  .steps li::before { content: ""; position: absolute; top: 0; left: 50%; width: 0.8rem; height: 0.8rem; margin-left: -0.4rem; box-sizing: border-box; border-radius: 50%; border: 2px solid currentColor; }
  .steps li::after { content: ""; position: absolute; top: 0.35rem; left: calc(-50% + 0.4rem); width: calc(100% - 0.8rem); height: 2px; background: currentColor; opacity: 0.4; }
  .steps li:first-child::after { display: none; }
  .steps li.done { opacity: 1; }
  .steps li.done::before { background: currentColor; }
  .steps li.now { opacity: 1; font-weight: 700; color: #c0392b; }
  .steps li.now::before { background: #c0392b; animation: pulse 1.6s ease-in-out infinite; }
  @keyframes pulse { 0%, 100% { box-shadow: 0 0 0 0 rgba(192, 57, 43, .5); } 50% { box-shadow: 0 0 0 6px rgba(192, 57, 43, 0); } }

  .smallprint { border: 1px dashed rgba(128, 128, 128, 0.5); border-radius: 0.5rem; padding: 1rem 1.25rem; font-size: 0.9rem; margin: 2rem 0; }
  .smallprint-label { margin: 0 0 0.6rem; text-transform: uppercase; letter-spacing: 0.14em; font-size: 0.7rem; opacity: 0.65; }
  .smallprint p:last-child { margin-bottom: 0; }

  @media (prefers-reduced-motion: reduce) {
    .vinyl, .steps li.now::before { animation: none; }
  }
</style>

<div class="newsletter">

  <div class="liner">
    <div class="vinyl" aria-hidden="true"></div>
    <p class="liner-kicker">Coming soon</p>
    <p class="liner-lead">A newsletter on the physics of handstand balance is on its way.</p>
  </div>

  <p>The physics of handstand balance delivered to your inbox, plus the occasional note that doesn’t fit in an article.</p>

  <p class="tracklist-label">Tracklist</p>
  <ol class="tracklist">
    <li>New posts on the physics of handstand balance <small>in your inbox</small></li>
    <li>Bonus track: the occasional note that doesn’t fit in an article <small>every now and then</small></li>
  </ol>

  <p>Leave your email address and I’ll write to you once it’s ready.</p>

  <ol class="steps" aria-label="Where the newsletter stands">
    <li class="done">Idea</li>
    <li class="now">Test pressing</li>
    <li>Setup</li>
    <li>Release</li>
  </ol>

  <p><a class="btn" href="https://docs.google.com/forms/d/e/1FAIpQLScUHUH19eT3a6SQB5pTEzOYSEjTDFkXbTV4GtIru3jY2EoDoA/viewform" target="_blank" rel="noopener">Join the list</a></p>

  <div class="smallprint">
    <p class="smallprint-label">Small print</p>
    <p>The form is hosted by Google Forms and opens in a new tab. I’ll use your email address only to tell you when the newsletter launches and to send it afterwards. I won’t share it with anyone, and you can ask me to delete it at any time. Details in the <a href="{{ '/privacy-policy/' | relative_url }}">privacy policy</a>. Prefer not to use the form? Write to <a href="mailto:benedettagiglio@gmail.com">benedettagiglio@gmail.com</a> with “Newsletter” in the subject.</p>
  </div>

</div>
