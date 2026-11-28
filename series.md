---
layout: page
title: "The handstand logs"
description: "All the posts of the handstand dilemma series in order: models, energy and mechanics to understand how handbalancing works."
permalink: /blog/series/
---

Handstands make one think of quiescence: they aren’t. Physically, the bodyweight sits above the hands, and any error grows exponentially. Staying up means correcting, continuously, with wrists and fingers that were never selected for the job. Evolution didn’t build sapiens to balance on hands, and yet humans learn to do it. That is what makes the handstand also philosophically interesting: handstands are punk.

In a way, handbalancing comes with a certain musicality: it’s not a state but an action. You stay balanced only by continuing to balance, and motor learning is the wildest process you can experience. The Handstand Dilemma is not the hunt for the ultimate handstand solution, but the search for a simple, direct question: why do humans get obsessed with learning useless things?

Inspired by a 45 rpm record: <strong>Part A</strong> treats the body as a single rigid block, <strong>Part B</strong> opens it up into an articulated one. Read the posts in order, or jump to the topic that interests you.

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign part_a = series_posts | where_exp: "post", "post.series_part != 'B'" %}
{% assign part_b = series_posts | where: "series_part", "B" %}

<style>
  .side { margin: 2.5rem 0; }
  .side-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 1rem; }
  /* 45 rpm disc: dark record, signal burst engraved in the groove */
  .side-disc {
    flex: none;
    width: 3.5rem;
    height: 3.5rem;
    border-radius: 50%;
    display: grid;
    place-items: center;
    font: 600 1.05rem/1 ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    color: #19f0ff;
    text-shadow: 0 0 6px rgba(25, 240, 255, 0.55);
    /* Side A: cyan signal */
    background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='49.4' fill='%2304050a' stroke='%2319f0ff' stroke-opacity='.5' stroke-width='1'/%3E%3Ccircle cx='50' cy='50' r='47' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='44.6' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='42.4' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Cpath d='M14.3,37.0 A38,38 0 0 1 26.6,20.1' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M85.7,63.0 A38,38 0 0 1 73.4,79.9' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M50.0,15.0 L51.4,13.1 L52.8,11.7 L54.3,11.2 L55.7,11.4 L57.0,12.5 L58.1,14.1 L59.0,16.0 L59.8,17.9 L60.6,19.4 L61.5,20.4 L62.5,20.9 L63.9,20.8 L65.5,20.3 L67.2,19.8 L69.0,19.3 L70.7,19.2 L72.1,19.5 L73.3,20.4 L74.0,21.6 L74.5,23.1 L74.7,24.8 L74.9,26.5 L75.1,28.0 L75.5,29.2 L76.2,30.2 L77.2,31.0 L78.4,31.7 L79.8,32.3 L81.2,33.0 L82.5,33.8 L83.4,34.9 L84.0,36.1 L84.3,37.4 L84.2,38.9 L84.0,40.3 L83.6,41.8 L83.3,43.1 L83.2,44.4 L83.3,45.7 L83.6,46.9 L84.1,48.1 L84.7,49.4 L85.3,50.7 L85.7,52.0 L85.9,53.3 L85.9,54.7 L85.5,56.0 L85.0,57.2 L84.3,58.4 L83.5,59.5 L82.7,60.6 L82.0,61.7 L81.5,62.9 L81.1,64.1 L80.8,65.3 L80.5,66.6 L80.2,67.9 L79.8,69.2 L79.3,70.4 L78.6,71.6 L77.7,72.6 L76.7,73.4 L75.6,74.2 L74.5,74.9 L73.3,75.6 L72.3,76.3 L71.2,77.0 L70.2,77.8 L69.3,78.7 L68.3,79.6 L67.3,80.5 L66.3,81.3 L65.2,82.0 L64.0,82.6 L62.8,83.1 L61.5,83.4 L60.3,83.7 L59.0,83.8 L57.7,83.9 L56.4,84.1 L55.1,84.2 L53.8,84.4 L52.6,84.6 L51.3,84.8 L50.0,85.0 L48.7,85.1 L47.4,85.2 L46.1,85.1 L44.8,84.9 L43.5,84.7 L42.3,84.3 L41.0,83.8 L39.8,83.4 L38.6,82.9 L37.5,82.4 L36.3,81.9 L35.1,81.4 L33.9,80.9 L32.7,80.4 L31.5,79.8 L30.4,79.2 L29.3,78.5 L28.3,77.7 L27.3,76.9 L26.3,75.9 L25.5,75.0 L24.6,74.0 L23.8,73.0 L23.0,72.0 L22.2,71.0 L21.4,70.0 L20.7,68.9 L19.9,67.9 L19.2,66.8 L18.6,65.6 L18.0,64.5 L17.5,63.3 L17.0,62.1 L16.6,60.8 L16.3,59.6 L16.0,58.3 L15.8,57.0 L15.6,55.8 L15.4,54.5 L15.3,53.2 L15.1,51.9 L15.0,50.6 L15.0,49.4 L15.0,48.1 L15.1,46.8 L15.2,45.5 L15.4,44.2 L15.7,42.9 L16.0,41.7 L16.4,40.4 L16.8,39.2 L17.2,38.0 L17.7,36.8 L18.2,35.6 L18.7,34.4 L19.3,33.3 L19.9,32.1 L20.6,31.0 L21.3,29.9 L22.0,28.9 L22.8,27.9 L23.7,26.9 L24.6,25.9 L25.5,25.0 L26.4,24.2 L27.4,23.3 L28.4,22.5 L29.5,21.7 L30.5,21.0 L31.6,20.3 L32.7,19.6 L33.8,18.9 L35.0,18.4 L36.1,17.8 L37.3,17.3 L38.6,16.9 L39.8,16.5 L41.0,16.2 L42.3,15.9 L43.6,15.6 L44.8,15.4 L46.1,15.2 L47.4,15.1 L48.7,15.0 L50.0,15.0Z' fill='none' stroke='%2319f0ff' stroke-opacity='.2' stroke-width='3.2' stroke-linejoin='round'/%3E%3Cpath d='M50.0,15.0 L51.4,13.1 L52.8,11.7 L54.3,11.2 L55.7,11.4 L57.0,12.5 L58.1,14.1 L59.0,16.0 L59.8,17.9 L60.6,19.4 L61.5,20.4 L62.5,20.9 L63.9,20.8 L65.5,20.3 L67.2,19.8 L69.0,19.3 L70.7,19.2 L72.1,19.5 L73.3,20.4 L74.0,21.6 L74.5,23.1 L74.7,24.8 L74.9,26.5 L75.1,28.0 L75.5,29.2 L76.2,30.2 L77.2,31.0 L78.4,31.7 L79.8,32.3 L81.2,33.0 L82.5,33.8 L83.4,34.9 L84.0,36.1 L84.3,37.4 L84.2,38.9 L84.0,40.3 L83.6,41.8 L83.3,43.1 L83.2,44.4 L83.3,45.7 L83.6,46.9 L84.1,48.1 L84.7,49.4 L85.3,50.7 L85.7,52.0 L85.9,53.3 L85.9,54.7 L85.5,56.0 L85.0,57.2 L84.3,58.4 L83.5,59.5 L82.7,60.6 L82.0,61.7 L81.5,62.9 L81.1,64.1 L80.8,65.3 L80.5,66.6 L80.2,67.9 L79.8,69.2 L79.3,70.4 L78.6,71.6 L77.7,72.6 L76.7,73.4 L75.6,74.2 L74.5,74.9 L73.3,75.6 L72.3,76.3 L71.2,77.0 L70.2,77.8 L69.3,78.7 L68.3,79.6 L67.3,80.5 L66.3,81.3 L65.2,82.0 L64.0,82.6 L62.8,83.1 L61.5,83.4 L60.3,83.7 L59.0,83.8 L57.7,83.9 L56.4,84.1 L55.1,84.2 L53.8,84.4 L52.6,84.6 L51.3,84.8 L50.0,85.0 L48.7,85.1 L47.4,85.2 L46.1,85.1 L44.8,84.9 L43.5,84.7 L42.3,84.3 L41.0,83.8 L39.8,83.4 L38.6,82.9 L37.5,82.4 L36.3,81.9 L35.1,81.4 L33.9,80.9 L32.7,80.4 L31.5,79.8 L30.4,79.2 L29.3,78.5 L28.3,77.7 L27.3,76.9 L26.3,75.9 L25.5,75.0 L24.6,74.0 L23.8,73.0 L23.0,72.0 L22.2,71.0 L21.4,70.0 L20.7,68.9 L19.9,67.9 L19.2,66.8 L18.6,65.6 L18.0,64.5 L17.5,63.3 L17.0,62.1 L16.6,60.8 L16.3,59.6 L16.0,58.3 L15.8,57.0 L15.6,55.8 L15.4,54.5 L15.3,53.2 L15.1,51.9 L15.0,50.6 L15.0,49.4 L15.0,48.1 L15.1,46.8 L15.2,45.5 L15.4,44.2 L15.7,42.9 L16.0,41.7 L16.4,40.4 L16.8,39.2 L17.2,38.0 L17.7,36.8 L18.2,35.6 L18.7,34.4 L19.3,33.3 L19.9,32.1 L20.6,31.0 L21.3,29.9 L22.0,28.9 L22.8,27.9 L23.7,26.9 L24.6,25.9 L25.5,25.0 L26.4,24.2 L27.4,23.3 L28.4,22.5 L29.5,21.7 L30.5,21.0 L31.6,20.3 L32.7,19.6 L33.8,18.9 L35.0,18.4 L36.1,17.8 L37.3,17.3 L38.6,16.9 L39.8,16.5 L41.0,16.2 L42.3,15.9 L43.6,15.6 L44.8,15.4 L46.1,15.2 L47.4,15.1 L48.7,15.0 L50.0,15.0Z' fill='none' stroke='%2319f0ff' stroke-opacity='.9' stroke-width='.9' stroke-linejoin='round'/%3E%3Ccircle cx='50' cy='50' r='21' fill='%23070910' stroke='%2319f0ff' stroke-opacity='.6' stroke-width='1.1'/%3E%3C/svg%3E") center / 100% 100% no-repeat;
  }
  /* Side B: magenta signal */
  #part-b .side-disc {
    color: #ff2bd6;
    text-shadow: 0 0 6px rgba(255, 43, 214, 0.55);
    background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='49.4' fill='%2304050a' stroke='%23ff2bd6' stroke-opacity='.5' stroke-width='1'/%3E%3Ccircle cx='50' cy='50' r='47' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='44.6' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='42.4' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Cpath d='M14.3,37.0 A38,38 0 0 1 26.6,20.1' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M85.7,63.0 A38,38 0 0 1 73.4,79.9' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M50.0,85.0 L48.6,86.9 L47.2,88.3 L45.7,88.8 L44.3,88.6 L43.0,87.5 L41.9,85.9 L41.0,84.0 L40.2,82.1 L39.4,80.6 L38.5,79.6 L37.5,79.1 L36.1,79.2 L34.5,79.7 L32.8,80.2 L31.0,80.7 L29.3,80.8 L27.9,80.5 L26.7,79.6 L26.0,78.4 L25.5,76.9 L25.3,75.2 L25.1,73.5 L24.9,72.0 L24.5,70.8 L23.8,69.8 L22.8,69.0 L21.6,68.3 L20.2,67.7 L18.8,67.0 L17.5,66.2 L16.6,65.1 L16.0,63.9 L15.7,62.6 L15.8,61.1 L16.0,59.7 L16.4,58.2 L16.7,56.9 L16.8,55.6 L16.7,54.3 L16.4,53.1 L15.9,51.9 L15.3,50.6 L14.7,49.3 L14.3,48.0 L14.1,46.7 L14.1,45.3 L14.5,44.0 L15.0,42.8 L15.7,41.6 L16.5,40.5 L17.3,39.4 L18.0,38.3 L18.5,37.1 L18.9,35.9 L19.2,34.7 L19.5,33.4 L19.8,32.1 L20.2,30.8 L20.7,29.6 L21.4,28.4 L22.3,27.4 L23.3,26.6 L24.4,25.8 L25.5,25.1 L26.7,24.4 L27.7,23.7 L28.8,23.0 L29.8,22.2 L30.7,21.3 L31.7,20.4 L32.7,19.5 L33.7,18.7 L34.8,18.0 L36.0,17.4 L37.2,16.9 L38.5,16.6 L39.7,16.3 L41.0,16.2 L42.3,16.1 L43.6,15.9 L44.9,15.8 L46.2,15.6 L47.4,15.4 L48.7,15.2 L50.0,15.0 L51.3,14.9 L52.6,14.8 L53.9,14.9 L55.2,15.1 L56.5,15.3 L57.7,15.7 L59.0,16.2 L60.2,16.6 L61.4,17.1 L62.5,17.6 L63.7,18.1 L64.9,18.6 L66.1,19.1 L67.3,19.6 L68.5,20.2 L69.6,20.8 L70.7,21.5 L71.7,22.3 L72.7,23.1 L73.7,24.1 L74.5,25.0 L75.4,26.0 L76.2,27.0 L77.0,28.0 L77.8,29.0 L78.6,30.0 L79.3,31.1 L80.1,32.1 L80.8,33.2 L81.4,34.4 L82.0,35.5 L82.5,36.7 L83.0,37.9 L83.4,39.2 L83.7,40.4 L84.0,41.7 L84.2,43.0 L84.4,44.2 L84.6,45.5 L84.7,46.8 L84.9,48.1 L85.0,49.4 L85.0,50.6 L85.0,51.9 L84.9,53.2 L84.8,54.5 L84.6,55.8 L84.3,57.1 L84.0,58.3 L83.6,59.6 L83.2,60.8 L82.8,62.0 L82.3,63.2 L81.8,64.4 L81.3,65.6 L80.7,66.7 L80.1,67.9 L79.4,69.0 L78.7,70.1 L78.0,71.1 L77.2,72.1 L76.3,73.1 L75.4,74.1 L74.5,75.0 L73.6,75.8 L72.6,76.7 L71.6,77.5 L70.5,78.3 L69.5,79.0 L68.4,79.7 L67.3,80.4 L66.2,81.1 L65.0,81.6 L63.9,82.2 L62.7,82.7 L61.4,83.1 L60.2,83.5 L59.0,83.8 L57.7,84.1 L56.4,84.4 L55.2,84.6 L53.9,84.8 L52.6,84.9 L51.3,85.0 L50.0,85.0Z' fill='none' stroke='%23ff2bd6' stroke-opacity='.2' stroke-width='3.2' stroke-linejoin='round'/%3E%3Cpath d='M50.0,85.0 L48.6,86.9 L47.2,88.3 L45.7,88.8 L44.3,88.6 L43.0,87.5 L41.9,85.9 L41.0,84.0 L40.2,82.1 L39.4,80.6 L38.5,79.6 L37.5,79.1 L36.1,79.2 L34.5,79.7 L32.8,80.2 L31.0,80.7 L29.3,80.8 L27.9,80.5 L26.7,79.6 L26.0,78.4 L25.5,76.9 L25.3,75.2 L25.1,73.5 L24.9,72.0 L24.5,70.8 L23.8,69.8 L22.8,69.0 L21.6,68.3 L20.2,67.7 L18.8,67.0 L17.5,66.2 L16.6,65.1 L16.0,63.9 L15.7,62.6 L15.8,61.1 L16.0,59.7 L16.4,58.2 L16.7,56.9 L16.8,55.6 L16.7,54.3 L16.4,53.1 L15.9,51.9 L15.3,50.6 L14.7,49.3 L14.3,48.0 L14.1,46.7 L14.1,45.3 L14.5,44.0 L15.0,42.8 L15.7,41.6 L16.5,40.5 L17.3,39.4 L18.0,38.3 L18.5,37.1 L18.9,35.9 L19.2,34.7 L19.5,33.4 L19.8,32.1 L20.2,30.8 L20.7,29.6 L21.4,28.4 L22.3,27.4 L23.3,26.6 L24.4,25.8 L25.5,25.1 L26.7,24.4 L27.7,23.7 L28.8,23.0 L29.8,22.2 L30.7,21.3 L31.7,20.4 L32.7,19.5 L33.7,18.7 L34.8,18.0 L36.0,17.4 L37.2,16.9 L38.5,16.6 L39.7,16.3 L41.0,16.2 L42.3,16.1 L43.6,15.9 L44.9,15.8 L46.2,15.6 L47.4,15.4 L48.7,15.2 L50.0,15.0 L51.3,14.9 L52.6,14.8 L53.9,14.9 L55.2,15.1 L56.5,15.3 L57.7,15.7 L59.0,16.2 L60.2,16.6 L61.4,17.1 L62.5,17.6 L63.7,18.1 L64.9,18.6 L66.1,19.1 L67.3,19.6 L68.5,20.2 L69.6,20.8 L70.7,21.5 L71.7,22.3 L72.7,23.1 L73.7,24.1 L74.5,25.0 L75.4,26.0 L76.2,27.0 L77.0,28.0 L77.8,29.0 L78.6,30.0 L79.3,31.1 L80.1,32.1 L80.8,33.2 L81.4,34.4 L82.0,35.5 L82.5,36.7 L83.0,37.9 L83.4,39.2 L83.7,40.4 L84.0,41.7 L84.2,43.0 L84.4,44.2 L84.6,45.5 L84.7,46.8 L84.9,48.1 L85.0,49.4 L85.0,50.6 L85.0,51.9 L84.9,53.2 L84.8,54.5 L84.6,55.8 L84.3,57.1 L84.0,58.3 L83.6,59.6 L83.2,60.8 L82.8,62.0 L82.3,63.2 L81.8,64.4 L81.3,65.6 L80.7,66.7 L80.1,67.9 L79.4,69.0 L78.7,70.1 L78.0,71.1 L77.2,72.1 L76.3,73.1 L75.4,74.1 L74.5,75.0 L73.6,75.8 L72.6,76.7 L71.6,77.5 L70.5,78.3 L69.5,79.0 L68.4,79.7 L67.3,80.4 L66.2,81.1 L65.0,81.6 L63.9,82.2 L62.7,82.7 L61.4,83.1 L60.2,83.5 L59.0,83.8 L57.7,84.1 L56.4,84.4 L55.2,84.6 L53.9,84.8 L52.6,84.9 L51.3,85.0 L50.0,85.0Z' fill='none' stroke='%23ff2bd6' stroke-opacity='.9' stroke-width='.9' stroke-linejoin='round'/%3E%3Ccircle cx='50' cy='50' r='21' fill='%23070910' stroke='%23ff2bd6' stroke-opacity='.6' stroke-width='1.1'/%3E%3C/svg%3E") center / 100% 100% no-repeat;
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
