---
layout: default
title: "Unraveling handstand balance"
description: "Models and mechanics explained step by step to understand why the handstand is unstable and what it takes to hold it."
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

  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: transparent; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

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

  <h1>Unraveling handstand balance</h1>
  <p class="lead">Why is a handstand unstable, and what does it take to hold one? A step-by-step physics model, built from the ground up.</p>
  <p>
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

  <p class="intro">A handstand looks like stillness. It isn’t. Handstand balance is unstable by construction. The human body is not designed to balance on its hands; being upside down is not what we evolved for. And yet humans learn to do it. The Handstand Dilemma exists because that ambivalence is fascinating, and I want to unpack it.</p>

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
  <p>I’m a biomedical engineer with a long-standing interest in movement, biomechanics and human performance. This project is where handstand practice and analytical reasoning meet. I don’t claim to have answers: the purpose of this project is to document my search for them. <em><a href="{{ '/about/' | relative_url }}">More about the project</a>.</em></p>

  <p><small>Want to follow along? <em><a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a></em>.</small></p>

</div>
