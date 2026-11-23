---
layout: page
title: "Series"
description: "All the posts of the handstand dilemma series in order: models, energy and mechanics to understand how handbalancing works."
permalink: /series/
---

A step-by-step exploration of the handstand, released like a 45 rpm record: <strong>Part A</strong> treats the body as a single rigid block, <strong>Part B</strong> opens it up into an articulated one. Read the posts in order, or jump to the topic that interests you.

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign part_a = series_posts | where_exp: "post", "post.series_part != 'B'" %}
{% assign part_b = series_posts | where: "series_part", "B" %}

<style>
  .side { margin: 2.5rem 0; }
  .side-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 1rem; }
  .side-disc {
    flex: none;
    width: 3.5rem;
    height: 3.5rem;
    border-radius: 50%;
    display: grid;
    place-items: center;
    font-size: 1.5rem;
    font-weight: 700;
    color: #fff;
    background: radial-gradient(circle, #c0392b 0 40%, #111 41% 100%);
    box-shadow: 0 0 0 2px rgba(128, 128, 128, 0.35);
  }
  .side-title { margin: 0; line-height: 1.2; }
  .side-subtitle { margin: 0; opacity: 0.7; font-size: 0.95rem; }
  .side ol { margin-top: 0; }
  .side li { margin-bottom: 0.8rem; }
  .side-empty { opacity: 0.7; font-style: italic; }
</style>

<section class="side" id="part-a">
  <div class="side-header">
    <div class="side-disc" aria-hidden="true">A</div>
    <div>
      <h2 class="side-title">Part A</h2>
      <p class="side-subtitle">The rigid body hypothesis</p>
    </div>
  </div>
  {% if part_a.size > 0 %}
  <ol>
    {% for post in part_a %}
    <li>
      <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a><br>
      <small>{{ post.description }}</small>
    </li>
    {% endfor %}
  </ol>
  {% endif %}
</section>

<section class="side" id="part-b">
  <div class="side-header">
    <div class="side-disc" aria-hidden="true">B</div>
    <div>
      <h2 class="side-title">Part B</h2>
      <p class="side-subtitle">The articulated body hypothesis</p>
    </div>
  </div>
  {% if part_b.size > 0 %}
  <ol>
    {% for post in part_b %}
    <li>
      <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a><br>
      <small>{{ post.description }}</small>
    </li>
    {% endfor %}
  </ol>
  {% else %}
  <p class="side-empty">Coming soon: the B side is still being recorded.</p>
  {% endif %}
</section>
