---
layout: default
title: "Handstand balance model: deep dive into why balancing upside down is so hard"
description: "Models and mechanics explained step by step to understand why the handstand is unstable and what it takes to hold it."
---

<h1>disassembling the dilemma</h1>

<p style="font-weight: 500;">Observe like a physicist.<br>Unpack like an engineer.<br>Experience like a practitioner.</p>

{% assign first_post = site.posts | where: "series_order", 1 | first %}
{% if first_post %}
<p><strong>New here?</strong><br> Start with <em><a href="{{ first_post.url | relative_url }}">{{ first_post.title }}</a></em>, or browse <em><a href="{{ '/series/' | relative_url }}">the complete series</a></em>.</p>
{% endif %}

<h2>Latest posts</h2>

{% for post in site.posts limit:5 %}
<article>
  <h3 style="font-size: 1.6rem;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  <p><small>{{ post.date | date: "%b %-d, %Y" }}</small></p>
  <div class="post-excerpt" style="text-align: justify;">{{ post.excerpt }}</div>
</article>
{% endfor %}

<p><a href="{{ '/series/' | relative_url }}">See all posts in the series →</a></p>

<p><small>Want to follow along? <a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a>. You can also read <a href="{{ '/about/' | relative_url }}">more about this project</a>.</small></p>
