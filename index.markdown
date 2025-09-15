---
layout: default
title: Poetry Collection
---

# Poetry Collection

A journey through words, emotions, and rhythmic expressions.

## Poems

<div class="post-list">
{% for post in site.posts limit:5 %}
  <article class="post-preview">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
    <p>{{ post.excerpt }}</p>
    <a href="{{ post.url | relative_url }}" class="read-more">Read More →</a>
  </article>
{% endfor %}
</div>

<div class="post-categories">
  <h2>Categories</h2>
  {% assign categories = site.categories | sort %}
  {% for category in categories %}
    <a href="/categories/{{ category | first | slugify }}/" class="category-link">
      {{ category | first }} ({{ category | last | size }})
    </a>
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

.post-preview {
    margin-bottom: 2em;
    padding-bottom: 1em;
    border-bottom: 1px solid var(--color-moss);
    background: white;
    padding: 1.5em;
    border-radius: 4px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
}

.post-preview h2 a {
    color: var(--color-forest);
    text-decoration: none;
    transition: color 0.3s;
}

.post-preview h2 a:hover {
    color: var(--color-earth);
}

.post-meta {
    color: var(--color-moss);
    font-size: 0.9em;
    font-style: italic;
}

.read-more {
    display: inline-block;
    margin-top: 1em;
    padding: 0.5em 1em;
    background: var(--color-forest);
    color: white;
    text-decoration: none;
    border-radius: 2px;
    transition: background-color 0.3s;
}

.read-more:hover {
    background: var(--color-moss);
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
