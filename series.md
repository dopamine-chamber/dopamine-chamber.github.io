---
layout: page
title: "Handstand physics: the complete series"
description: "All the posts of handstand balance model."
permalink: /series/
---

A step-by-step exploration of the handstand through the eyes of a practitioner. Read the posts in order, or jump to the topic that interests you.

<ul>
{% assign ordered = site.posts | sort: "title" %}
{% for post in ordered %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a><br>
    <small>{{ post.description }}</small>
  </li>
{% endfor %}
</ul>
