---
layout: default
title: "Movement is a way of thinking"
description: "Physics lessons in an upside-down context: exploring the handstand balance"
---

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign start_post = series_posts | first %}

<style>
  .home { text-align: left; }
  .home h1 { font-size: 2.1rem; font-weight: 600; line-height: 1.2; margin: 1.5rem 0 0.6rem; text-align: left; }
  .home h2 { font-size: 1.4rem; font-weight: 600; margin: 2.5rem 0 0.8rem; text-align: left; }
  .home p { text-align: left; }
  .home .lead { font-size: 1.15rem; line-height: 1.5; margin-bottom: 1.2rem; }
  .home .intro { text-align: justify; hyphens: auto; -webkit-hyphens: auto; }

  .home a.btn, .home a.btn:visited {
    display: inline-block; padding: 0.55rem 1.1rem; margin: 0 0.5rem 0.5rem 0;
    border: 1px solid #222; border-radius: 6px; color: #222; text-decoration: none;
  }
  .home a.btn-primary, .home a.btn-primary:visited { background: #222; color: #fff; }
  .home a.btn:hover { opacity: 0.85; text-decoration: none; }
  .home .cta { text-align: center; }
  .home .cta a.btn { margin: 0 0.25rem 0.5rem; }

  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: transparent; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

  .music { max-width: 660px; margin: 1.5rem auto; }
  .music-label { margin: 0 0 0.4rem; font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase; color: #6b6b6b; }
  .music iframe { display: block; width: 100%; height: 120px; border: 1px solid #e5e5e5; border-radius: 8px; }

  .page-content .path-list { display: block; list-style: none; margin: 1rem 0; padding: 0; text-align: left; }
  .path-list li { display: flex; gap: 1rem; align-items: flex-start; padding: 0.9rem 0; margin: 0; border-top: 1px solid #e5e5e5; }
  .path-list li:last-child { border-bottom: 1px solid #e5e5e5; }
  .path-list .step { flex: 0 0 2rem; height: 2rem; border: 1px solid #222; border-radius: 50%; text-align: center; line-height: 2rem; font-size: 0.9rem; }
  .path-list a { font-weight: 600; display: block; }
  .path-list small { display: block; margin-top: 0.2rem; color: #6b6b6b; line-height: 1.4; }
  .page-content .latest-list { display: block; list-style: none; margin: 1rem 0; padding: 0; text-align: left; }
  .latest-list li { padding: 0.9rem 0; margin: 0; border-top: 1px solid #e5e5e5; }
  .latest-list li:last-child { border-bottom: 1px solid #e5e5e5; }
  .latest-list .meta { font-size: 0.85rem; color: #6b6b6b; }
  .latest-list .tag { margin-left: 0.6rem; padding: 0.05rem 0.5rem; border: 1px solid #222; border-radius: 999px; font-size: 0.75rem; }
  .latest-list a { display: block; margin-top: 0.2rem; font-weight: 600; }
  .latest-list small { display: block; margin-top: 0.2rem; color: #6b6b6b; line-height: 1.4; }
</style>

<div class="home">

  <h1>Movement is a way of thinking</h1>
  <p class="lead">It's how we experience the world. It's a way to look at human potential. The Handstand Dilemma is an editorial project where physical and philosophical approaches meet to explore the handstand phenomenon, deconstructing it from the ground up. Same physical principles, different context. </p>
  <p class="cta">
    <a class="btn btn-primary" href="{{ start_post.url | relative_url }}">Start here</a>
    <a class="btn" href="{{ '/blog/' | relative_url }}">Browse all posts</a>
  </p>

  <figure class="hero-anim">
    <iframe
      src="{{ '/assets/img/handstand_home.html' | relative_url }}"
      title="Animation of a stick figure doing a cartwheel and settling into a handstand, swaying slightly to keep its balance"
      scrolling="no">
    </iframe>
  </figure>

  <div class="music">
    <p class="music-label">Now playing</p>
    <iframe
      src="https://bandcamp.com/EmbeddedPlayer/album=1524188113/size=large/bgcol=ffffff/linkcol=222222/tracklist=false/artwork=small/transparent=true/"
      title="Dopamine Chamber by Fontaines D.C. on Bandcamp"
      loading="lazy"
      seamless>
      <a href="https://fontainesdc.bandcamp.com/album/dopamine-chamber">Dopamine Chamber by Fontaines D.C.</a>
    </iframe>
  </div>

  <div class="intro">
  <p>A handstand looks like stillness. It isn’t. Physically, the body’s centre of mass sits above the hands, and any error grows exponentially, roughly doubling every quarter of a second. Staying up means correcting, continuously, with wrists and fingers that were never selected for the job. Evolution didn’t build us to balance on our hands. And yet humans learn to do it.</p>

  <p>That is what makes the handstand philosophically interesting. Heraclitus saw the harmony of the world in tension, like the bow and the lyre: opposing forces that hold each other in place. The handstand is that idea in a body: not a state but an action. You stay balanced only by continuing to balance. If it were stable, it would be a pose, like lying down, and it would be worth little; its value comes from its precariousness.</p>

  <p>It is also a small Sisyphus. No handstand is final: it always ends. Camus asks us to imagine Sisyphus happy. But Sisyphus is condemned to his rock, while we choose our handstands, and that may be the whole point. Anyone who practices knows the value lies not in the arrival but in the repeated
