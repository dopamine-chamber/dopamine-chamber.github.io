---
layout: default
title: "Signals from noise"
description: "Blog on motor learning: error, adaptation and convergence toward reality."
---

{% assign series_posts = site.posts | where_exp: "post", "post.series_order" | sort: "series_order" %}
{% assign start_post = series_posts | first %}
{% assign start_url = start_post.url | default: '/blog/' %}
{% assign part_a = series_posts | where_exp: "post", "post.series_part != 'B'" %}
{% assign part_b = series_posts | where: "series_part", "B" %}

<style>
  /* ---------- Base ---------- */
  .home { text-align: left; }
  .home h1 { font-size: 2.1rem; font-weight: 600; line-height: 1.2; margin: 1.5rem 0 0.6rem; text-align: center; }
  .home h2 { font-size: 1.75rem; font-weight: 600; line-height: 1.25; margin: 2.8rem 0 0.9rem; text-align: left; hyphens: manual; -webkit-hyphens: manual; }
  @media (max-width: 700px) { .home h2 { font-size: 1.45rem; } }
  .home p { text-align: left; }

  /* Justified blocks: the rule must target the paragraphs, because
     ".home p" above sets text-align on the <p> itself and would win
     over anything set on the container. */
  .home .intro p,
  .home .prose p { text-align: justify; hyphens: auto; -webkit-hyphens: auto; }
  .home .intro p.lead,
  .home .intro p.closing { text-align: left; hyphens: manual; -webkit-hyphens: manual; }

  /* ---------- Intro ---------- */
  .home .lead { font-size: 1.15rem; line-height: 1.5; margin-bottom: 1.2rem; }
  .home .intro-body p { margin: 0 0 0.8rem; }
  .home .closing { margin: 1.4rem 0 0; padding-top: 1rem; border-top: 1px solid #e5e5e5; font-size: 1.05rem; line-height: 1.5; }

  /* ---------- Links ---------- */
  .home a:not(.btn):not(.side-card) { color: #3a3fd1; }
  .home a:not(.btn):not(.side-card):visited { color: #6b3fc9; }
  .home a:not(.btn):not(.side-card):hover,
  .home a:not(.btn):not(.side-card):focus { color: #7b3ff2; }

  /* ---------- 45 rpm discs: dark record, signal burst engraved in the groove ---------- */
  .home {
    --disc-a: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='49.4' fill='%2304050a' stroke='%2319f0ff' stroke-opacity='.5' stroke-width='1'/%3E%3Ccircle cx='50' cy='50' r='47' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='44.6' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='42.4' fill='none' stroke='%2319f0ff' stroke-opacity='.12' stroke-width='.7'/%3E%3Cpath d='M14.3,37.0 A38,38 0 0 1 26.6,20.1' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M85.7,63.0 A38,38 0 0 1 73.4,79.9' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M50.0,15.0 L51.4,13.1 L52.8,11.7 L54.3,11.2 L55.7,11.4 L57.0,12.5 L58.1,14.1 L59.0,16.0 L59.8,17.9 L60.6,19.4 L61.5,20.4 L62.5,20.9 L63.9,20.8 L65.5,20.3 L67.2,19.8 L69.0,19.3 L70.7,19.2 L72.1,19.5 L73.3,20.4 L74.0,21.6 L74.5,23.1 L74.7,24.8 L74.9,26.5 L75.1,28.0 L75.5,29.2 L76.2,30.2 L77.2,31.0 L78.4,31.7 L79.8,32.3 L81.2,33.0 L82.5,33.8 L83.4,34.9 L84.0,36.1 L84.3,37.4 L84.2,38.9 L84.0,40.3 L83.6,41.8 L83.3,43.1 L83.2,44.4 L83.3,45.7 L83.6,46.9 L84.1,48.1 L84.7,49.4 L85.3,50.7 L85.7,52.0 L85.9,53.3 L85.9,54.7 L85.5,56.0 L85.0,57.2 L84.3,58.4 L83.5,59.5 L82.7,60.6 L82.0,61.7 L81.5,62.9 L81.1,64.1 L80.8,65.3 L80.5,66.6 L80.2,67.9 L79.8,69.2 L79.3,70.4 L78.6,71.6 L77.7,72.6 L76.7,73.4 L75.6,74.2 L74.5,74.9 L73.3,75.6 L72.3,76.3 L71.2,77.0 L70.2,77.8 L69.3,78.7 L68.3,79.6 L67.3,80.5 L66.3,81.3 L65.2,82.0 L64.0,82.6 L62.8,83.1 L61.5,83.4 L60.3,83.7 L59.0,83.8 L57.7,83.9 L56.4,84.1 L55.1,84.2 L53.8,84.4 L52.6,84.6 L51.3,84.8 L50.0,85.0 L48.7,85.1 L47.4,85.2 L46.1,85.1 L44.8,84.9 L43.5,84.7 L42.3,84.3 L41.0,83.8 L39.8,83.4 L38.6,82.9 L37.5,82.4 L36.3,81.9 L35.1,81.4 L33.9,80.9 L32.7,80.4 L31.5,79.8 L30.4,79.2 L29.3,78.5 L28.3,77.7 L27.3,76.9 L26.3,75.9 L25.5,75.0 L24.6,74.0 L23.8,73.0 L23.0,72.0 L22.2,71.0 L21.4,70.0 L20.7,68.9 L19.9,67.9 L19.2,66.8 L18.6,65.6 L18.0,64.5 L17.5,63.3 L17.0,62.1 L16.6,60.8 L16.3,59.6 L16.0,58.3 L15.8,57.0 L15.6,55.8 L15.4,54.5 L15.3,53.2 L15.1,51.9 L15.0,50.6 L15.0,49.4 L15.0,48.1 L15.1,46.8 L15.2,45.5 L15.4,44.2 L15.7,42.9 L16.0,41.7 L16.4,40.4 L16.8,39.2 L17.2,38.0 L17.7,36.8 L18.2,35.6 L18.7,34.4 L19.3,33.3 L19.9,32.1 L20.6,31.0 L21.3,29.9 L22.0,28.9 L22.8,27.9 L23.7,26.9 L24.6,25.9 L25.5,25.0 L26.4,24.2 L27.4,23.3 L28.4,22.5 L29.5,21.7 L30.5,21.0 L31.6,20.3 L32.7,19.6 L33.8,18.9 L35.0,18.4 L36.1,17.8 L37.3,17.3 L38.6,16.9 L39.8,16.5 L41.0,16.2 L42.3,15.9 L43.6,15.6 L44.8,15.4 L46.1,15.2 L47.4,15.1 L48.7,15.0 L50.0,15.0Z' fill='none' stroke='%2319f0ff' stroke-opacity='.2' stroke-width='3.2' stroke-linejoin='round'/%3E%3Cpath d='M50.0,15.0 L51.4,13.1 L52.8,11.7 L54.3,11.2 L55.7,11.4 L57.0,12.5 L58.1,14.1 L59.0,16.0 L59.8,17.9 L60.6,19.4 L61.5,20.4 L62.5,20.9 L63.9,20.8 L65.5,20.3 L67.2,19.8 L69.0,19.3 L70.7,19.2 L72.1,19.5 L73.3,20.4 L74.0,21.6 L74.5,23.1 L74.7,24.8 L74.9,26.5 L75.1,28.0 L75.5,29.2 L76.2,30.2 L77.2,31.0 L78.4,31.7 L79.8,32.3 L81.2,33.0 L82.5,33.8 L83.4,34.9 L84.0,36.1 L84.3,37.4 L84.2,38.9 L84.0,40.3 L83.6,41.8 L83.3,43.1 L83.2,44.4 L83.3,45.7 L83.6,46.9 L84.1,48.1 L84.7,49.4 L85.3,50.7 L85.7,52.0 L85.9,53.3 L85.9,54.7 L85.5,56.0 L85.0,57.2 L84.3,58.4 L83.5,59.5 L82.7,60.6 L82.0,61.7 L81.5,62.9 L81.1,64.1 L80.8,65.3 L80.5,66.6 L80.2,67.9 L79.8,69.2 L79.3,70.4 L78.6,71.6 L77.7,72.6 L76.7,73.4 L75.6,74.2 L74.5,74.9 L73.3,75.6 L72.3,76.3 L71.2,77.0 L70.2,77.8 L69.3,78.7 L68.3,79.6 L67.3,80.5 L66.3,81.3 L65.2,82.0 L64.0,82.6 L62.8,83.1 L61.5,83.4 L60.3,83.7 L59.0,83.8 L57.7,83.9 L56.4,84.1 L55.1,84.2 L53.8,84.4 L52.6,84.6 L51.3,84.8 L50.0,85.0 L48.7,85.1 L47.4,85.2 L46.1,85.1 L44.8,84.9 L43.5,84.7 L42.3,84.3 L41.0,83.8 L39.8,83.4 L38.6,82.9 L37.5,82.4 L36.3,81.9 L35.1,81.4 L33.9,80.9 L32.7,80.4 L31.5,79.8 L30.4,79.2 L29.3,78.5 L28.3,77.7 L27.3,76.9 L26.3,75.9 L25.5,75.0 L24.6,74.0 L23.8,73.0 L23.0,72.0 L22.2,71.0 L21.4,70.0 L20.7,68.9 L19.9,67.9 L19.2,66.8 L18.6,65.6 L18.0,64.5 L17.5,63.3 L17.0,62.1 L16.6,60.8 L16.3,59.6 L16.0,58.3 L15.8,57.0 L15.6,55.8 L15.4,54.5 L15.3,53.2 L15.1,51.9 L15.0,50.6 L15.0,49.4 L15.0,48.1 L15.1,46.8 L15.2,45.5 L15.4,44.2 L15.7,42.9 L16.0,41.7 L16.4,40.4 L16.8,39.2 L17.2,38.0 L17.7,36.8 L18.2,35.6 L18.7,34.4 L19.3,33.3 L19.9,32.1 L20.6,31.0 L21.3,29.9 L22.0,28.9 L22.8,27.9 L23.7,26.9 L24.6,25.9 L25.5,25.0 L26.4,24.2 L27.4,23.3 L28.4,22.5 L29.5,21.7 L30.5,21.0 L31.6,20.3 L32.7,19.6 L33.8,18.9 L35.0,18.4 L36.1,17.8 L37.3,17.3 L38.6,16.9 L39.8,16.5 L41.0,16.2 L42.3,15.9 L43.6,15.6 L44.8,15.4 L46.1,15.2 L47.4,15.1 L48.7,15.0 L50.0,15.0Z' fill='none' stroke='%2319f0ff' stroke-opacity='.9' stroke-width='.9' stroke-linejoin='round'/%3E%3Ccircle cx='50' cy='50' r='21' fill='%23070910' stroke='%2319f0ff' stroke-opacity='.6' stroke-width='1.1'/%3E%3C/svg%3E");
    --disc-b: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='49.4' fill='%2304050a' stroke='%23ff2bd6' stroke-opacity='.5' stroke-width='1'/%3E%3Ccircle cx='50' cy='50' r='47' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='44.6' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Ccircle cx='50' cy='50' r='42.4' fill='none' stroke='%23ff2bd6' stroke-opacity='.12' stroke-width='.7'/%3E%3Cpath d='M14.3,37.0 A38,38 0 0 1 26.6,20.1' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M85.7,63.0 A38,38 0 0 1 73.4,79.9' fill='none' stroke='%23fff' stroke-opacity='.09' stroke-width='2.2' stroke-linecap='round'/%3E%3Cpath d='M50.0,85.0 L48.6,86.9 L47.2,88.3 L45.7,88.8 L44.3,88.6 L43.0,87.5 L41.9,85.9 L41.0,84.0 L40.2,82.1 L39.4,80.6 L38.5,79.6 L37.5,79.1 L36.1,79.2 L34.5,79.7 L32.8,80.2 L31.0,80.7 L29.3,80.8 L27.9,80.5 L26.7,79.6 L26.0,78.4 L25.5,76.9 L25.3,75.2 L25.1,73.5 L24.9,72.0 L24.5,70.8 L23.8,69.8 L22.8,69.0 L21.6,68.3 L20.2,67.7 L18.8,67.0 L17.5,66.2 L16.6,65.1 L16.0,63.9 L15.7,62.6 L15.8,61.1 L16.0,59.7 L16.4,58.2 L16.7,56.9 L16.8,55.6 L16.7,54.3 L16.4,53.1 L15.9,51.9 L15.3,50.6 L14.7,49.3 L14.3,48.0 L14.1,46.7 L14.1,45.3 L14.5,44.0 L15.0,42.8 L15.7,41.6 L16.5,40.5 L17.3,39.4 L18.0,38.3 L18.5,37.1 L18.9,35.9 L19.2,34.7 L19.5,33.4 L19.8,32.1 L20.2,30.8 L20.7,29.6 L21.4,28.4 L22.3,27.4 L23.3,26.6 L24.4,25.8 L25.5,25.1 L26.7,24.4 L27.7,23.7 L28.8,23.0 L29.8,22.2 L30.7,21.3 L31.7,20.4 L32.7,19.5 L33.7,18.7 L34.8,18.0 L36.0,17.4 L37.2,16.9 L38.5,16.6 L39.7,16.3 L41.0,16.2 L42.3,16.1 L43.6,15.9 L44.9,15.8 L46.2,15.6 L47.4,15.4 L48.7,15.2 L50.0,15.0 L51.3,14.9 L52.6,14.8 L53.9,14.9 L55.2,15.1 L56.5,15.3 L57.7,15.7 L59.0,16.2 L60.2,16.6 L61.4,17.1 L62.5,17.6 L63.7,18.1 L64.9,18.6 L66.1,19.1 L67.3,19.6 L68.5,20.2 L69.6,20.8 L70.7,21.5 L71.7,22.3 L72.7,23.1 L73.7,24.1 L74.5,25.0 L75.4,26.0 L76.2,27.0 L77.0,28.0 L77.8,29.0 L78.6,30.0 L79.3,31.1 L80.1,32.1 L80.8,33.2 L81.4,34.4 L82.0,35.5 L82.5,36.7 L83.0,37.9 L83.4,39.2 L83.7,40.4 L84.0,41.7 L84.2,43.0 L84.4,44.2 L84.6,45.5 L84.7,46.8 L84.9,48.1 L85.0,49.4 L85.0,50.6 L85.0,51.9 L84.9,53.2 L84.8,54.5 L84.6,55.8 L84.3,57.1 L84.0,58.3 L83.6,59.6 L83.2,60.8 L82.8,62.0 L82.3,63.2 L81.8,64.4 L81.3,65.6 L80.7,66.7 L80.1,67.9 L79.4,69.0 L78.7,70.1 L78.0,71.1 L77.2,72.1 L76.3,73.1 L75.4,74.1 L74.5,75.0 L73.6,75.8 L72.6,76.7 L71.6,77.5 L70.5,78.3 L69.5,79.0 L68.4,79.7 L67.3,80.4 L66.2,81.1 L65.0,81.6 L63.9,82.2 L62.7,82.7 L61.4,83.1 L60.2,83.5 L59.0,83.8 L57.7,84.1 L56.4,84.4 L55.2,84.6 L53.9,84.8 L52.6,84.9 L51.3,85.0 L50.0,85.0Z' fill='none' stroke='%23ff2bd6' stroke-opacity='.2' stroke-width='3.2' stroke-linejoin='round'/%3E%3Cpath d='M50.0,85.0 L48.6,86.9 L47.2,88.3 L45.7,88.8 L44.3,88.6 L43.0,87.5 L41.9,85.9 L41.0,84.0 L40.2,82.1 L39.4,80.6 L38.5,79.6 L37.5,79.1 L36.1,79.2 L34.5,79.7 L32.8,80.2 L31.0,80.7 L29.3,80.8 L27.9,80.5 L26.7,79.6 L26.0,78.4 L25.5,76.9 L25.3,75.2 L25.1,73.5 L24.9,72.0 L24.5,70.8 L23.8,69.8 L22.8,69.0 L21.6,68.3 L20.2,67.7 L18.8,67.0 L17.5,66.2 L16.6,65.1 L16.0,63.9 L15.7,62.6 L15.8,61.1 L16.0,59.7 L16.4,58.2 L16.7,56.9 L16.8,55.6 L16.7,54.3 L16.4,53.1 L15.9,51.9 L15.3,50.6 L14.7,49.3 L14.3,48.0 L14.1,46.7 L14.1,45.3 L14.5,44.0 L15.0,42.8 L15.7,41.6 L16.5,40.5 L17.3,39.4 L18.0,38.3 L18.5,37.1 L18.9,35.9 L19.2,34.7 L19.5,33.4 L19.8,32.1 L20.2,30.8 L20.7,29.6 L21.4,28.4 L22.3,27.4 L23.3,26.6 L24.4,25.8 L25.5,25.1 L26.7,24.4 L27.7,23.7 L28.8,23.0 L29.8,22.2 L30.7,21.3 L31.7,20.4 L32.7,19.5 L33.7,18.7 L34.8,18.0 L36.0,17.4 L37.2,16.9 L38.5,16.6 L39.7,16.3 L41.0,16.2 L42.3,16.1 L43.6,15.9 L44.9,15.8 L46.2,15.6 L47.4,15.4 L48.7,15.2 L50.0,15.0 L51.3,14.9 L52.6,14.8 L53.9,14.9 L55.2,15.1 L56.5,15.3 L57.7,15.7 L59.0,16.2 L60.2,16.6 L61.4,17.1 L62.5,17.6 L63.7,18.1 L64.9,18.6 L66.1,19.1 L67.3,19.6 L68.5,20.2 L69.6,20.8 L70.7,21.5 L71.7,22.3 L72.7,23.1 L73.7,24.1 L74.5,25.0 L75.4,26.0 L76.2,27.0 L77.0,28.0 L77.8,29.0 L78.6,30.0 L79.3,31.1 L80.1,32.1 L80.8,33.2 L81.4,34.4 L82.0,35.5 L82.5,36.7 L83.0,37.9 L83.4,39.2 L83.7,40.4 L84.0,41.7 L84.2,43.0 L84.4,44.2 L84.6,45.5 L84.7,46.8 L84.9,48.1 L85.0,49.4 L85.0,50.6 L85.0,51.9 L84.9,53.2 L84.8,54.5 L84.6,55.8 L84.3,57.1 L84.0,58.3 L83.6,59.6 L83.2,60.8 L82.8,62.0 L82.3,63.2 L81.8,64.4 L81.3,65.6 L80.7,66.7 L80.1,67.9 L79.4,69.0 L78.7,70.1 L78.0,71.1 L77.2,72.1 L76.3,73.1 L75.4,74.1 L74.5,75.0 L73.6,75.8 L72.6,76.7 L71.6,77.5 L70.5,78.3 L69.5,79.0 L68.4,79.7 L67.3,80.4 L66.2,81.1 L65.0,81.6 L63.9,82.2 L62.7,82.7 L61.4,83.1 L60.2,83.5 L59.0,83.8 L57.7,84.1 L56.4,84.4 L55.2,84.6 L53.9,84.8 L52.6,84.9 L51.3,85.0 L50.0,85.0Z' fill='none' stroke='%23ff2bd6' stroke-opacity='.9' stroke-width='.9' stroke-linejoin='round'/%3E%3Ccircle cx='50' cy='50' r='21' fill='%23070910' stroke='%23ff2bd6' stroke-opacity='.6' stroke-width='1.1'/%3E%3C/svg%3E");
  }

  /* ---------- Buttons ---------- */
  .home a.btn, .home a.btn:visited {
    display: inline-block; padding: 0.55rem 1.1rem; margin: 0 0.5rem 0.5rem 0;
    border: 1px solid #222; border-radius: 6px; color: #222; text-decoration: none;
  }
  .home a.btn-primary, .home a.btn-primary:visited { background: #222; color: #fff; }
  .home a.btn:hover { opacity: 0.85; text-decoration: none; }

  .home .cta { text-align: center; }
  .home p.cta a.btn {
    display: inline-flex; align-items: center; gap: 0.6rem;
    margin: 0 0.25rem 0.5rem; padding: 0.4rem 1.2rem 0.4rem 0.5rem;
    border-radius: 999px;
  }
  /* 45 rpm icon in the buttons: cyan on the primary, magenta on the secondary */
  .home p.cta a.btn::before {
    content: ""; flex: none; width: 1.7rem; height: 1.7rem; border-radius: 50%;
    background:
      radial-gradient(circle, #f5f0e6 0 1.4px, transparent 1.9px),
      var(--disc-b) center / 100% 100% no-repeat;
    box-shadow: 0 0 0 1px rgba(255, 43, 214, 0.35);
  }
  .home p.cta a.btn-primary::before {
    background:
      radial-gradient(circle, #f5f0e6 0 1.4px, transparent 1.9px),
      var(--disc-a) center / 100% 100% no-repeat;
    box-shadow: 0 0 0 1px rgba(25, 240, 255, 0.45);
  }
  .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: btn-spin 1.8s linear infinite; }
  @keyframes btn-spin { to { transform: rotate(360deg); } }
  @media (prefers-reduced-motion: reduce) {
    .home p.cta a.btn:hover::before, .home p.cta a.btn:focus-visible::before { animation: none; }
  }

  /* ---------- Hero animation ---------- */
  .hero-anim { margin: 1.5rem 0; }
  .hero-anim iframe { display: block; width: 100%; aspect-ratio: 20 / 9; max-height: 70vh; border: 0; background: #04050a; border-radius: 8px; }
  @media (max-width: 700px) { .hero-anim iframe { aspect-ratio: 35 / 27; } }

  /* ---------- Series: Side A / Side B ---------- */
  .sides { display: flex; flex-wrap: wrap; gap: 0.75rem; margin: 1rem 0; }
  .home a.side-card, .home a.side-card:visited {
    flex: 1 1 15rem; display: flex; align-items: center; gap: 0.9rem;
    padding: 0.9rem 1rem; border: 1px solid #e5e5e5; border-radius: 8px;
    color: inherit; text-decoration: none;
  }
  .home a.side-card:hover { border-color: #0bc3d3; text-decoration: none; }
  .home a.side-card:nth-child(2):hover { border-color: #d11fb0; }
  .side-disc {
    flex: none; width: 2.8rem; height: 2.8rem; border-radius: 50%;
    display: grid; place-items: center;
    font: 600 0.85rem/1 ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    color: #19f0ff; text-shadow: 0 0 6px rgba(25, 240, 255, 0.55);
    /* Side A: cyan signal */
    background: var(--disc-a) center / 100% 100% no-repeat;
    transition: box-shadow 0.2s;
  }
  /* Side B: magenta signal */
  .side-card:nth-child(2) .side-disc { color: #ff2bd6; text-shadow: 0 0 6px rgba(255, 43, 214, 0.55); background: var(--disc-b) center / 100% 100% no-repeat; }
  .home a.side-card:hover .side-disc { box-shadow: 0 0 12px rgba(25, 240, 255, 0.45); }
  .home a.side-card:nth-child(2):hover .side-disc { box-shadow: 0 0 12px rgba(255, 43, 214, 0.45); }
  .side-text strong { display: block; }
  .side-text small { display: block; margin-top: 0.15rem; color: #6b6b6b; line-height: 1.4; }

  /* ---------- Latest posts ---------- */
  .home .latest-list { display: flex; flex-direction: column; gap: 1rem; margin: 1rem 0; }
  .home .latest-item a { font-weight: 600; font-style: normal; text-decoration: none; }
  .home .latest-item a:hover { text-decoration: underline; }
  .home .latest-item .meta { margin-top: 0.15rem; font-size: 0.85rem; color: #6b6b6b; }
  .home .see-all a { text-decoration: underline; }

  /* ---------- Now playing ---------- */
  .music { max-width: 660px; margin: 2.5rem auto 1rem; }
  .music-label { margin: 0 0 0.4rem; font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase; color: #6b6b6b; }
  .music iframe { display: block; width: 100%; height: 120px; border: 1px solid #e5e5e5; border-radius: 8px; }
</style>

<div class="home">

  <section class="intro">
    <p class="lead">A collection of notes on learning, adaptation, and the strange machinery that transforms repetition into skill.</p>
      </section>

  <!-- Hero animation -->
  <figure class="hero-anim">
    <iframe
      src="{{ '/assets/img/home/signal_noise_home.html' | relative_url }}"
      title="Animation of a noisy signal on an oscilloscope: a prediction model starts as a hallucination and converges toward the true signal as the error shrinks"
      scrolling="no">
    </iframe>
  </figure>

  <p class="cta">
    <a class="btn btn-primary" href="{{ start_url | relative_url }}">Start here</a>
    <a class="btn" href="{{ '/blog/' | relative_url }}">Browse all posts</a>
  </p>

  <!-- What you’re getting into -->
<h2>What you’re getting into: come for the quiet, stay for the search</h2>

Every movement begins as a hallucination, a guess about the world. The nervous system builds a model, and the muscles put it to the test. Error is reality’s response. Motor learning is how our guesses improve: as error is generated, the model updates. What we call learning is a prediction engine slowly converging toward reality.

{% include feedback-loop.html
   step1="the guess meets reality"
   step2="error is generated"
   step3="the model updates"
   repeat="Repeat thousands of times." %}

   <strong>Signals from noise</strong> is a philosophy of movement: an editorial project that explores the human machine beyond the ego. We don’t judge errors: we use them as the ultimate form of data our brain learns from.

  <!-- Series -->
  <h2>Follow the logs</h2>
<div class="sides">
  <a class="side-card" href="{{ '/blog/series/#part-a' | relative_url }}">
    <span class="side-disc" aria-hidden="true">A</span>
    <span class="side-text">
      <strong>Part A</strong>
      <small>The rigid body hypothesis · {{ part_a.size }} post{% if part_a.size != 1 %}s{% endif %}</small>
    </span>
  </a>
  <a class="side-card" href="{{ '/blog/series/#part-b' | relative_url }}">
    <span class="side-disc" aria-hidden="true">B</span>
    <span class="side-text">
      <strong>Part B</strong>
      <small>The articulated body hypothesis · {% if part_b.size > 0 %}{{ part_b.size }} post{% if part_b.size != 1 %}s{% endif %}{% else %}coming soon{% endif %}</small>
    </span>
  </a>
</div>
<p><a href="{{ '/blog/series/' | relative_url }}">See the whole series</a></p>

  <p><em>It’s also a quiet Sisyphus. No handstand is final: it always ends. Camus asks us to imagine Sisyphus happy. But Sisyphus is condemned to his rock, while we choose our handstands, and that may be the whole point. Anyone who practices knows the value lies not in the arrival but in the repeated attempt.</em></p>

  <!-- Who writes this -->
  <h2>Who writes this</h2>
  <p>Biomedical engineer, independent writer and circus amateur, exploring movement as a meeting place between science, art and philosophy. At its core, this project is not about the clinical physics of handstands. It’s a window into how complex human systems mobilize and dialectically negotiate their physical, emotional and intellectual dimensions to learn, adapt and remain stable in changing environments. There are no answers here, only questions to navigate, and each one opens onto another in a never-ending why. <em><a href="{{ '/about/' | relative_url }}">More about the project</a>.</em></p>

  <!-- Latest posts -->
  <h2>Latest posts</h2>
  <div class="latest-list">
    {% for post in site.posts limit: 3 %}
    <div class="latest-item">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <div class="meta">
        {% assign author = post.author | default: site.author %}
        {% if author %}{{ author }} · {% endif %}
        {% if post.series %}{{ post.series }}{% if post.series_order %} (part {{ post.series_order }}){% endif %} · {% elsif post.series_order %}Series, part {{ post.series_order }} · {% elsif post.label %}{{ post.label }} · {% endif %}
        {{ post.date | date: "%b %-d, %Y" }}
      </div>
    </div>
    {% endfor %}
  </div>
  <p class="see-all"><a href="{{ '/blog/' | relative_url }}">See all posts</a></p>

  <p><small>Want to follow along? <em><a href="{{ '/feed.xml' | relative_url }}">Subscribe via RSS</a></em>.</small></p>

  <!-- Now playing -->
  <div class="music">
    <p class="music-label">Now playing</p>
    <iframe
      src="https://bandcamp.com/EmbeddedPlayer/album=1524188113/size=large/bgcol=ffffff/linkcol=222222/tracklist=false/artwork=small/transparent=true/"
      title="Dopamine Chamber by Fontaines D.C. on Bandcamp"
      loading="lazy">
      <a href="https://fontainesdc.bandcamp.com/album/dopamine-chamber">Dopamine Chamber by Fontaines D.C.</a>
    </iframe>
  </div>

</div>
