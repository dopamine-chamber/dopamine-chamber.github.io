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

  .sides { display: flex; flex-wrap: wrap; gap: 0.75rem; margin: 1rem 0; }
  .home a.side-card, .home a.side-card:visited {
    flex: 1 1 15rem; display: flex; align-items: center; gap: 0.9rem;
    padding: 0.9rem 1rem; border: 1px solid #e5e5e5; border-radius: 8px;
    color: inherit; text-decoration: none;
  }
  .home a.side-card:hover { border-color: #222; text-decoration: none; }
  .side-disc {
    flex: none; width: 2.6rem; height: 2.6rem; border-radius: 50%;
    display: grid; place-items: center; color: #fff; font-weight: 700; font-size: 1.1rem;
    background: radial-gradient(circle, #c0392b 0 40%, #111 41% 100%);
  }
  .side-text strong { display: block; }
  .side-text small { display: block; margin-top: 0.15rem; color: #6b6b6b; line-height: 1.4; }

  .page-content .latest-list { display: block; list-style: none; margin: 1rem 0; padding: 0; text-align: left; }
  .latest-list li { padding: 0.9rem 0; margin: 0; border-top: 1px solid #e5e5e5; }
  .latest-list li:last-child { border-bottom: 1px solid #e5e5e5; }
  .latest-list .meta { font-size: 0.85rem; color: #6b6b6b; }
  .latest-list .tag { margin-left: 0.6rem; padding: 0.05rem 0.5rem; border: 1px solid #222; border-radius: 999px; font-size: 0.75rem; }
  .latest-list a { display: block; margin-top: 0.2rem; font-weight: 600; }
  .latest-list small { display: block; margin-top: 0.2rem; color: #6b6b6b; line-height: 1.4; }

  .music { max-width: 660px; margin: 2.5rem auto 1rem; }
  .music-label { margin: 0 0 0.4rem; font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase; color: #6b6b6b; }
  .music iframe { display: block; width: 100%; height: 120px; border: 1px solid #e5e5e5; border-radius: 8px; }
</style>

<div class="home">

  <h1>Movement is a way of thinking</h1>
  <p class="lead">It's how we experience the world. It's a way to look at human potential. The Handstand Dilemma is an editorial project where physical and philosophical approaches meet to explore the handstand phenomenon, deconstructing it from the ground up. Same physical principles, different context. </p>

  <figure class="hero-anim">
    <iframe
      src="{{ '/assets/img/handstand_home.html' | relative_url }}"
      title="Animation of a stick figure doing a cartwheel and settling into a handstand, swaying slightly to keep its balance"
      scrolling="no">
    </iframe>
  </figure>

  <p class="cta">
    <a class="btn btn-primary" href="{{ start_post.url | relative_url }}">Start here</a>
    <a class="btn" href="{{ '/blog/' | relative_url }}">Browse all posts</a>
  </p>

  <div class="intro">

  <h2>What you're getting into: come for the quiet, stay for the search</h2>
  <p>A handstand looks like stillness. It isn’t. Physically, the body’s centre of mass sits above the hands, and any error grows exponentially, roughly doubling every quarter of a second. Staying up means correcting, continuously, with wrists and fingers that were never selected for the job. In a way, movement tied to the handstand comes with a certain musicality. And in fact, rhythm is the foundation of the idea behind this project. It is what inspired it and what continues to help it grow.</p>

  <p>Evolution didn’t build us to balance on our hands. And yet humans learn to do it. That is what makes the handstand also philosophically interesting. Heraclitus saw the harmony of the world in tension, like the bow and the lyre: opposing forces that hold each other in place. The handstand is that idea in a body: not a state but an action. You stay balanced only by continuing to balance. If it were stable, it would be a pose, like lying down, and it would be worth little; its value comes from its precariousness.</p>

  <p>The Handstand Dilemma is about that tension: a posture that looks like stillness, is made of constant motion, and serves no purpose except itself. I want to understand why we keep doing it.</p>
</div>

  <h2>Follow the series</h2>
  <p>The series is built like a 45 rpm record: one handstand, two sides. Part A treats the body as a single rigid block; Part B opens it up into an articulated one.</p>
  <div class="sides">
    <a class="side-card" href="{{ '/series/#part-a' | relative_url }}">
      <span class="side-disc" aria-hidden="true">A</span>
      <span class="side-text">
        <strong>Part A</strong>
        <small>The rigid body hypothesis · {{ part_a.size }} post{% if part_a.size != 1 %}s{% endif %}</small>
      </span>
    </a>
    <a class="side-card" href="{{ '/series/#part-b' | relative_url }}">
      <span class="side-disc" aria-hidden="true">B</span>
      <span class="side-text">
        <strong>Part B</strong>
        <small>The articulated body hypothesis · {% if part_b.size > 0 %}{{ part_b.size }} post{% if part_b.size != 1 %}s{% endif %}{% else %}coming soon{% endif %}</small>
      </span>
    </a>
  </div>
  <p><a href="{{ '/series/' | relative_url }}">See the whole series</a></p>

  <p>It is also a small Sisyphus. No handstand is final: it always ends. Camus asks us to imagine Sisyphus happy. But Sisyphus is condemned to his rock, while we choose our handstands, and that may be the whole point. Anyone who practices knows the value lies not in the arrival but in the repeated attempt.</p>

  <h2>Who writes this</h2>
  <p>I’m a biomedical engineer with a long-standing interest in movement, art and human performance. This project is where handstand practice and analytical reasoning meet. I don’t claim to have answers: the purpose of this project is to document my search for them. <em><a href="{{ '/about/' | relative_url }}">More about the project</a>.</em></p>

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

  <p><small>Want to follow along? <em><a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a></em>.</small></p>

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

</div>
