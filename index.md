---
layout: default
title: "The physics of the handstand: why balancing upside down is so hard"
description: "Models, energy and mechanics explained step by step to understand why the handstand is unstable and what it takes to hold it."
---

<h1>Disassembling the dilemma</h1>

<p><em>Observe the phenomenon like a physicist. Unpack the phenomenon like an engineer. Experience the phenomenon like a practitioner.</em></p>

<p>If handbalancing is your love language, come down to the handstand rabbit hole</p>

{% assign first_post = site.posts | where: "series_order", 1 | first %}
{% if first_post %}
<p><strong>New here?</strong> Start with <a href="{{ first_post.url | relative_url }}">{{ first_post.title }}</a>, or browse <a href="{{ '/series/' | relative_url }}">the complete series</a>.</p>
{% endif %}

<h2>Latest posts</h2>

{% for post in site.posts limit:5 %}
<article>
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  <p><small>{{ post.date | date: "%b %-d, %Y" }}</small></p>
  <p>{{ post.description | default: post.excerpt | strip_html | truncate: 200 }}</p>
</article>
{% endfor %}

<p><a href="{{ '/series/' | relative_url }}">See all posts in the series →</a></p>

<p><small>Want to follow along? <a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a>. You can also read <a href="{{ '/about/' | relative_url }}">more about this project</a>.</small></p>
