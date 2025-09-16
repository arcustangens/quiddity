---
layout: default
title: Quiddity
---

<div class="post-list">
{% for post in site.posts limit:5 %}
  <article class="post-preview">
    <a href="{{ post.url | relative_url }}" class="post-link">
      <h2>{{ post.title }}</h2>
      {% if post.date %}
      <p class="post-meta">
          {% assign date_format = post.date_format | default: "%Y" %}
          {% if post.date_format == "month_year" %}
              {{ post.date | date: "%B %Y" }}
          {% else %}
              {{ post.date | date: date_format }}
          {% endif %}
      </p>
      {% endif %}
      <p class="post-excerpt">{{ post.excerpt }}</p>
    </a>
  </article>
{% endfor %}
</div>

<style>
:root {
    --color-forest: #2c4a3e;    /* Dark forest green for primary elements */
    --color-earth: #5e4238;     /* Rich earth brown for secondary elements */
    --color-moss: #4a5d4c;      /* Muted moss green for accents */
    --font-main: "EB Garamond", Georgia, serif;
    --font-headers: var(--font-main);
}

body {
    background-color: #f4f1eb;
    color: #2a2a2a;
    font-family: var(--font-main);
    font-size: 18px;
    line-height: 1.6;
}

h1, h2 {
    color: var(--color-forest);
}

.post-list {
    margin: 2em 0;
}

.post-list {
    position: relative;
}

.post-preview {
    margin-bottom: 3em;
    padding: 2em;
    background: white;
    border-radius: 4px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
    position: relative;
}

.post-preview:not(:last-child)::after {
    content: "";
    position: absolute;
    bottom: -1.5em;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 1px;
    background: var(--color-moss);
    opacity: 0.4;
}

.post-link {
    display: block;
    text-decoration: none;
    color: inherit;
    transition: all 0.3s ease;
}

.post-preview h2 {
    color: var(--color-forest);
    margin-top: 0;
    transition: color 0.3s;
}

.post-preview:hover h2 {
    color: var(--color-earth);
}

.post-meta {
    color: var(--color-moss);
    font-size: 0.9em;
    font-style: italic;
}

.post-excerpt {
    margin: 1em 0 0;
    color: #2a2a2a;
}

.post-categories {
    margin: 2em 0;
}

.category-link {
    display: inline-block;
    margin: 0.3em;
    padding: 0.5em 1em;
    background: var(--color-moss);
    color: white;
    border-radius: 2px;
    text-decoration: none;
    transition: all 0.3s;
}

.category-link:hover {
    background: var(--color-earth);
}

.timeline-nav {
    background: white;
    padding: 1.5em;
    border-radius: 4px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    margin: 2em 0;
}

.timeline-nav h2 {
    color: var(--color-forest);
    margin-top: 0;
}

.month-group {
    margin: 0.5em 0;
}

.month-group summary {
    cursor: pointer;
    padding: 0.5em;
    background: var(--color-forest);
    color: white;
    border-radius: 2px;
    transition: background-color 0.3s;
}

.month-group summary:hover {
    background: var(--color-moss);
}

.month-group ul {
    list-style: none;
    padding-left: 1.5em;
    margin: 0.5em 0;
}

.month-group a {
    color: var(--color-earth);
    text-decoration: none;
    transition: color 0.3s;
}

.month-group a:hover {
    color: var(--color-forest);
}
</style>
