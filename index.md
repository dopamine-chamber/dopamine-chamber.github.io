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
  .home p.cta a.btn {
    display: inline-flex; align-items: center; gap: 0.6rem;
    margin: 0 0.25rem 0.5rem; padding: 0.4rem 1.2rem 0.4rem 0.5rem;
    border-radius: 999px;
  }
  .home p.cta a.btn::before {
    content: ""; flex: none; width: 1.7rem; height: 1.7rem; border-radius: 50%;
    background:
      conic-gradient(from 20deg, transparent 0 20%, rgba(255,255,255,.2) 25%, transparent 30% 70%, rgba(255,255,255,.2) 75%, transparent 80%),
      radial-gradient(circle, #f5f0e6 0 8%, #c0392b 9% 32%, transparent 33%),
      repeating-radial-gradient(circle, #111 0 1.5px, #262626 2.5px 3.5px);
    box-shadow: 0 0 0 1px rgba(128, 128, 128, 0.5);
  }
  .home p.cta a.btn-primary::before { box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.4); }
  .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: btn-spin 1.8s linear infinite; }
  @keyframes btn-spin { to { transform: rotate(360deg); } }
  @media (prefers-reduced-motion: reduce) {
    .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: none; }
  }

  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: transparent; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

  .music { max-width: 660px; margin: 2.5rem auto 1rem; }
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

  <div class="intro">
  <p>A handstand looks like stillness. It isn’t. Physically, the body’s centre of mass sits above the hands, and any error grows exponentially, roughly doubling every quarter of a second. Staying up means correcting, continuously, with wrists and fingers that were never selected for the job. Evolution didn’t build us to balance on our hands. And yet humans learn to do it.</p>

  <p>That is what makes the handstand philosophically interesting. Heraclitus saw the harmony of the world in tension, like the bow and the lyre: opposing forces that hold each other in place. The handstand is that idea in a body: not a state but an action. You stay balanced only by continuing to balance. If it were stable, it would be a pose, like lying down, and it would be worth little; its value comes from its precariousness.</p>

  <p>It is also a small Sisyphus. No handstand is final: it always ends. Camus asks us to imagine Sisyphus happy. But Sisyphus is condemned to his rock, while we choose our handstands, and that may be the whole point. Anyone who practices knows the value lies not in the arrival but in the repeated attempt.</p>

  <p>The Handstand Dilemma is about that tension: a posture that looks like stillness, is made of constant motion, and serves no purpose except itself. I want to understand why we keep doing it.</p>
</div>

  <h2>Follow the series</h2>
  <p>Read the posts in order, or jump to the topic that interests you.</p>
  <ol class="path-list">
  {% for post in series_posts %}
    <li>
      <span class="step">{{ post.series_order }}</span>
      <div>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <small>{{ post.description | truncatewords: 22 }}</small>
      </div>
    </li>
  {% endfor %}
  </ol>

    <h2>Latest posts</h2>
  <ul class="latest-list">
  {% for post in site.posts limit: 3 %}
    <li>
      <span class="meta">{{ post.date | date: "%b %-d, %Y" }}</span>{% if post.series_order %}<span class="tag">Series, part {{ post.series_order }}</span>{% elsif post.label %}<span class="tag">{{ post.label }}</span>{% endif %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <small>{{ post.description | truncatewords: 22 }}</small>
    </li>
  {% endfor %}
  </ul>
  <p><a href="{{ '/blog/' | relative_url }}">See all posts</a></p>

  <h2>Who writes this</h2>
  <p>I’m a biomedical engineer with a long-standing interest in movement, art and human performance. This project is where handstand practice and analytical reasoning meet. I don’t claim to have answers: the purpose of this project is to document my search for them. <em><a href="{{ '/about/' | relative_url }}">More about the project</a>.</em></p>

  <p><small>Want to follow along? <em><a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a></em>.</small></p>

  <div class="music">
    <p class="music-label">Now playing</p>
    <iframe
      src="https://bandcamp.com/EmbeddedPlayer/track=2663334220/size=large/bgcol=ffffff/linkcol=222222/tracklist=false/artwork=small/transparent=true/"
      title="Japan by Fontaines D.C. on Bandcamp"
      loading="lazy"
      seamless>
      <a href="https://fontainesdc.bandcamp.com/track/japan">Japan by Fontaines D.C.</a>
    </iframe>
  </div>

</div>
