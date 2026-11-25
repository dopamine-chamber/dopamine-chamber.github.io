---
layout: default
title: "Movement is a way of thinking"
description: "Physics lessons in an upside-down context: exploring the handstand balance"
---

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign start_post = series_posts | first %}
{% assign part_a = series_posts | where_exp: "post", "post.series_part != 'B'" %}
{% assign part_b = series_posts | where: "series_part", "B" %}

<style>
  .home { text-align: left; }
  .home h1 { font-size: 2.1rem; font-weight: 600; line-height: 1.2; margin: 1.5rem 0 0.6rem; text-align: left; }
  .home h2 { font-size: 1.75rem; font-weight: 600; line-height: 1.25; margin: 2.8rem 0 0.9rem; text-align: left; hyphens: manual; -webkit-hyphens: manual; }
  @media (max-width: 700px) { .home h2 { font-size: 1.45rem; } }
  .home p { text-align: left; }
  .home .lead { font-size: 1.15rem; line-height: 1.5; margin-bottom: 1.2rem; }
  .home .intro { text-align: justify; hyphens: auto; -webkit-hyphens: auto; }

  .home a:not(.btn):not(.side-card) { color: #3a3fd1; }
  .home a:not(.btn):not(.side-card):visited { color: #6b3fc9; }
  .home a:not(.btn):not(.side-card):hover,
  .home a:not(.btn):not(.side-card):focus { color: #7b3ff2; }

  .home a.btn, .home a.btn:visited {
    display: inline-block; padding: 0.55rem 1.1rem; margin: 0 0.5rem 0.5rem 0;
    border: 1px solid #222; border-radius: 6px; color: #222; text-decoration: none;
  }
  .home a.btn-primary, .home a.btn-primary:visited { background: #222; color: #fff; }
  .home a.btn:hover { opacity: 0.85; text-decoration: none; }

  .home .cta { text-align: center; }
  .home p.cta a.btn {
    display: inline-flex; align-items: center; gap: 0.6rem;
    margin: 0 0.25rem 0.5rem; padding: 0.4rem 1.2rem 0.4rem 0.5rem;
    border-radius: 999px;
  }
  /* LP icon in the buttons: label in link blue (primary) and violet (secondary) */
  .home p.cta a.btn::before {
    content: ""; flex: none; width: 1.7rem; height: 1.7rem; border-radius: 50%;
    background:
      conic-gradient(from 20deg, transparent 0 20%, rgba(255,255,255,.2) 25%, transparent 30% 70%, rgba(255,255,255,.2) 75%, transparent 80%),
      radial-gradient(circle, #f5f0e6 0 8%, #6b3fc9 9% 32%, transparent 33%),
      repeating-radial-gradient(circle, #111 0 1.5px, #262626 2.5px 3.5px);
    box-shadow: 0 0 0 1px rgba(128, 128, 128, 0.5);
  }
  .home p.cta a.btn-primary::before {
    background:
      conic-gradient(from 20deg, transparent 0 20%, rgba(255,255,255,.2) 25%, transparent 30% 70%, rgba(255,255,255,.2) 75%, transparent 80%),
      radial-gradient(circle, #f5f0e6 0 8%, #3a3fd1 9% 32%, transparent 33%),
      repeating-radial-gradient(circle, #111 0 1.5px, #262626 2.5px 3.5px);
    box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.4);
  }
  .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: btn-spin 1.8s linear infinite; }
  @keyframes btn-spin { to { transform: rotate(360deg); } }
  @media (prefers-reduced-motion: reduce) {
    .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: none; }
  }

  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: transparent; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

  .sides { display: flex; flex-wrap: wrap; gap: 0.75rem; margin: 1rem 0; }
  .home a.side-card, .home a.side-card:visited {
    flex: 1 1 15rem; display: flex; align-items: center; gap: 0.9rem;
    padding: 0.9rem 1rem; border: 1px solid #e5e5e5; border-radius: 8px;
    color: inherit; text-decoration: none;
  }
  .home a.side-card:hover { border-color: #3a3fd1; text-decoration: none;
