---
layout: page
title: "Handstand physics: the complete series"
description: "All the posts of the handstand dilemma series in order: models, energy and mechanics to understand how handbalancing works."
permalink: /series/
---

A step-by-step exploration of the handstand. Read the posts in order, or jump to the topic that interests you.

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
<ol>
{% for post in series_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a><br>
    <small>{{ post.description }}</small>
  </li>
{% endfor %}
</ol>
