---
layout: default
title: "The physics of handbalancing"
description: "Models and mechanics explained step by step to understand why the handstand is unstable and what it takes to hold it."
---

<h2>disassembling the dilemma</h2>

<style>
  .hero-anim {
    margin: 0;
  }
  .hero-anim iframe {
    display: block;
    width: 100%;
    aspect-ratio: 20 / 9;
    max-height: 70vh;
    border: 0;
  }
  @media (max-width: 700px) {
    .hero-anim iframe {
      aspect-ratio: 35 / 27;
    }
  }
  .hero-anim figcaption {
    font-size: 0.9rem;
    text-align: center;
    opacity: 0.75;
    margin-top: 0.5rem;
  }
</style>

<figure class="hero-anim">
  <iframe
    src="assets/img/handstand_home.html"
    title="Animation of a stick figure doing a cartwheel and settling into a handstand, swaying slightly to keep its balance"
    scrolling="no">
  </iframe>
</figure>
     
<p style="font-weight: 100">
  Observe like a physicist. Unpack like an engineer. Experience like a practitioner.
</p>

{% assign first_post = site.posts | where: "series_order", 1 | first %}
{% if first_post %}
<p><strong>New here? Dive deep into the handstand rabbit hole and discover why balancing upside down is so hard. </strong><br> Start with <em><a href="{{ first_post.url | relative_url }}">{{ first_post.title }}</a></em>, or browse <em><a href="{{ '/series/' | relative_url }}">the complete series</a></em>.</p>
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
