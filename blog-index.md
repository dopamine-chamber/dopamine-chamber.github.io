---
layout: page
title: Blog
has_children: true
nav_order: 2
permalink: /blog/
description: Notes on biologial systems updating their models through experience, error and feedback.
---

<style>
  .post-list li h2 {
    font-size: 1.15rem;
    line-height: 1.3;
    font-weight: 700;
    margin: 0.2rem 0 0.4rem;
  }
</style>

<ul class="post-list">
{% for post in site.posts %}
  <li>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncatewords: 40 }}</p>{% endif %}
  </li>
{% endfor %}
</ul>
