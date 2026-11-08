---
layout: page
title: Blog
permalink: /blog/
description: All the posts on the physics of the handstand, from newest to oldest.
---

<ul class="post-list">
{% for post in site.posts %}
  <li>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncatewords: 40 }}</p>{% endif %}
  </li>
{% endfor %}
</ul>
