---
layout: default
title: "Movement is a way of thinking"
description: "Physics lessons in an upside-down context: exploring the handstand balance"
---

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign start_post = series_posts | first %}
{% assign start_url = start_post.url | default: '/blog/' %}
{% assign part_a = series_posts | where_exp: "post", "post.series_part != 'B'" %}
{% assign part_b = series_posts | where: "series_part", "B" %}

<style>
  /* ---------- Base ---------- */
  .home { text-align: left; }
  .home h1 { font-size: 2.1rem; font-weight: 600; line-height: 1.2; margin: 1.5rem 0 0.6rem; text-align: center; }
  .home h2 { font-size: 1.75rem; font-weight: 600; line-height: 1.25; margin: 2.8rem 0 0.9rem; text-align: left; hyphens: manual; -webkit-hyphens: manual; }
  @media (max-width: 700px) { .home h2 { font-size: 1.45rem; } }
  .home p { text-align: left; }

  /* Justified blocks: the rule must target the paragraphs, because
     ".home p" above sets text-align on the <p> itself and would win
     over anything set on the container. */
  .home .intro p,
  .home .prose p { text-align: justify; hyphens: auto; -webkit-hyphens: auto; }
  .home .intro p.lead,
  .home .intro p.closing { text-align: left; hyphens: manual; -webkit-hyphens: manual; }

  /* ---------- Intro ---------- */
  .home .lead { font-size: 1.15rem; line-height: 1.5; margin-bottom: 1.2rem; }
  .home .intro-body p { margin: 0 0 0.8rem; }
  .home .closing { margin: 1.4rem 0 0; padding-top: 1rem; border-top: 1px solid #e5e5e5; font-size: 1.05rem; line-height: 1.5; }

  /* ---------- Links ---------- */
  .home a:not(.btn):not(.side-card) { color: #3a3fd1; }
  .home a:not(.btn):not(.side-card):visited { color: #6b3fc9; }
  .home a:not(.btn):not(.side-card):hover,
  .home a:not(.btn):not(.side-card):focus { color: #7b3ff2; }

  /* ---------- Buttons ---------- */
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

  /* ---------- Hero animation ---------- */
  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: transparent; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

  /* ---------- Series: Side A / Side B ---------- */
  .sides { display: flex; flex-wrap: wrap; gap: 0.75rem; margin: 1rem 0; }
  .home a.side-card, .home a.side-card:visited {
    flex: 1 1 15rem; display: flex; align-items: center; gap: 0.9rem;
    padding: 0.9rem 1rem; border: 1px solid #e5e5e5; border-radius: 8px;
    color: inherit; text-decoration: none;
  }
  .home a.side-card:hover { border-color: #3a3fd1; text-decoration: none; }
  .home a.side-card:nth-child(2):hover { border-color: #6b3fc9; }
  .side-disc {
    flex: none; width: 2.6rem; height: 2.6rem; border-radius: 50%;
    display: grid; place-items: center; color: #fff; font-weight: 700; font-size: 1.1rem;
    /* Side A: link blue label */
    background: radial-gradient(circle, #3a3fd1 0 40%, #111 41% 100%);
  }
  /* Side B: visited violet label */
  .side-card:nth-child(2) .side-disc { background: radial-gradient(circle, #6b3fc9 0 40%, #111 41% 100%); }
  .side-text strong { display: block; }
  .side-text small { display: block; margin-top: 0.15rem; color: #6b6b6b; line-height: 1.4; }

  /* ---------- Latest posts ---------- */
  .home .latest-list { display: flex; flex-direction: column; gap: 1rem; margin: 1rem 0; }
  .home .latest-item a { font-weight: 600; font-style: normal; text-decoration: none; }
  .home .latest-item a:hover { text-decoration: underline; }
  .home .latest-item .meta { margin-top: 0.15rem; font-size: 0.85rem; color: #6b6b6b; }
  .home .see-all a { text-decoration: underline; }

  /* ---------- Now playing ---------- */
  .music { max-width: 660px; margin: 2.5rem auto 1rem; }
  .music-label { margin: 0 0 0.4rem; font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase; color: #6b6b6b; }
  .music iframe { display: block; width: 100%; height: 120px; border: 1px solid #e5e5e5; border-radius: 8px; }
</style>

<div class="home">

  <h1>Welcome to the handstand black hole</h1>

  <!-- Intro -->
  <section class="intro">
    <p class="lead">A chamber for studying movement, learning, adaptation, and the strange machinery that transforms repetition into skill.</p>
    <div class="intro-body">
      <p><strong>The nervous system as a prediction machine.</strong> Every skill begins as a <strong>hallucination</strong>; error is reality’s response to the model.</p>
      <p><strong>Anatomical wires as feedback loops.</strong> Reality disagrees, error is generated, the model updates. Repeat thousands of times.</p>
      <p>Error isn’t an error: it’s the ultimate form of data. Handstands are a dataset full of errors. <strong>The Handstand Dilemma</strong> is an editorial project where physical and philosophical approaches meet to disassemble, explore, and digest this process.</p>
    </div>
    <p class="closing"><strong>What we call learning is a prediction engine slowly converging toward reality.</strong></p>
  </section>

  <!-- Hero animation -->
  <figure class="hero-anim">
    <iframe
      src="{{ '/assets/img/handstand_home.html' | relative_url }}"
      title="Animation of a stick figure doing a cartwheel and settling into a handstand, swaying slightly to keep its balance"
      scrolling="no">
    </iframe>
  </figure>

  <p class="cta">
    <a class="btn btn-primary" href="{{ start_url | relative_url }}">Start here</a>
    <a class="btn" href="{{ '/blog/' | relative_url }}">Browse all posts</a>
  </p>

  <!-- What you’re getting into -->
  <div class="prose">
    <h2>What you’re getting into: come for the quiet, stay for the search</h2>
    <p>Handstands make one think of quiescence: they aren’t. Physically, the bodyweight sits above the hands, and any error grows exponentially. Staying up means correcting, continuously, with wrists and fingers that were never selected for the job. Evolution didn’t build sapiens to balance on hands, and yet humans learn to do it. That is what makes the handstand also philosophically interesting: <strong>handstands are punk.</strong></p>
    <p>In a way, handbalancing comes with a certain musicality: it’s not a state but an action. You stay balanced only by continuing to balance, and <strong>motor learning</strong> is the wildest process you can experience. The Handstand Dilemma is not the hunt for the ultimate handstand solution, but the search for a simple, direct question: why do humans get obsessed with learning useless things?</p>
  </div>

  <!-- Series -->
  <h2>Follow the series</h2>
  <p>Inspired by a 45 rpm record: one handstand, two sides. Part A treats the body as a single rigid block; Part B opens it up into an articulated one.</p>
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

  <p><em>It’s also a quiet Sisyphus. No handstand is final: it always ends. Camus asks us to imagine Sisyphus happy. But Sisyphus is condemned to his rock, while we choose our handstands, and that may be the whole point. Anyone who practices knows the value lies not in the arrival but in the repeated attempt.</em></p>

  <!-- Who writes this -->
  <h2>Who writes this</h2>
  <p>Biomedical engineer, independent writer and amateur circus artist, exploring movement as a meeting place between science, art and philosophy. At its core, this project is not about the clinical physics of handstands. It’s a window into how complex human systems mobilize and dialectically negotiate their physical, emotional and intellectual dimensions to learn, adapt and remain stable in changing environments. There are no answers here, only questions to navigate, and each one opens onto another in a never-ending why. <em><a href="{{ '/about/' | relative_url }}">More about the project</a>.</em></p>

  <!-- Latest posts -->
  <h2>Latest posts</h2>
  <div class="latest-list">
    {% for post in site.posts limit: 3 %}
    <div class="latest-item">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <div class="meta">
        {% assign author = post.author | default: site.author %}
        {% if author %}{{ author }} · {% endif %}
        {% if post.series %}{{ post.series }}{% if post.series_order %} (part {{ post.series_order }}){% endif %} · {% elsif post.series_order %}Series, part {{ post.series_order }} · {% elsif post.label %}{{ post.label }} · {% endif %}
        {{ post.date | date: "%b %-d, %Y" }}
      </div>
    </div>
    {% endfor %}
  </div>
  <p class="see-all"><a href="{{ '/blog/' | relative_url }}">See all posts</a></p>

  <p><small>Want to follow along? <em><a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a></em>.</small></p>

  <!-- Now playing -->
  <div class="music">
    <p class="music-label">Now playing</p>
    <iframe
      src="https://bandcamp.com/EmbeddedPlayer/album=1524188113/size=large/bgcol=ffffff/linkcol=222222/tracklist=false/artwork=small/transparent=true/"
      title="Dopamine Chamber by Fontaines D.C. on Bandcamp"
      loading="lazy">
      <a href="https://fontainesdc.bandcamp.com/album/dopamine-chamber">Dopamine Chamber by Fontaines D.C.</a>
    </iframe>
  </div>

</div>
