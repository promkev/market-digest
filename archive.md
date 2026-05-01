---
layout: default
title: Archive
permalink: /archive/
---

<div class="hero-bar">
  <div class="hero-inner">
    <div class="hero-info">
      <h2>Archive</h2>
      <div class="hero-meta">Browse all past trading day digests</div>
    </div>
    <div style="display:flex; gap:8px;">
      <a href="{{ '/' | relative_url }}" class="btn btn-hero-outline">← Today</a>
      <a href="https://github.com/promkev/market-digest" class="btn btn-hero-outline">GitHub</a>
    </div>
  </div>
</div>

<main>
  {% assign all_archive = site.pages | where_exp: "item", "item.url contains '/archive/'" %}
  {% assign count = 0 %}
  {% for p in all_archive %}
    {% if p.url != '/archive/' %}
      {% assign count = count | plus: 1 %}
    {% endif %}
  {% endfor %}

  {% if count > 0 %}
    <h3 style="font-size:14px;font-weight:600;text-transform:uppercase;letter-spacing:0.5px;color:var(--text-muted);margin-bottom:16px;">
      {{ count }} trading day{% if count > 1 %}s{% endif %} archived
    </h3>
    <ul class="archive-list">
      {% for entry in all_archive %}
        {% if entry.url != '/archive/' %}
        <li>
          <a href="{{ entry.url | relative_url }}">{{ entry.url | remove: '/archive/' | remove: '.html' | date: "%A, %B %-d, %Y" }}</a>
          <span class="date">{{ entry.url | remove: '/archive/' | remove: '.html' }}</span>
        </li>
        {% endif %}
      {% endfor %}
    </ul>
  {% else %}
    <div class="empty-state">
      <h2>No archived digests yet 📭</h2>
      <p style="color: var(--text-secondary);">Daily digests will appear here after each trading day.</p>
    </div>
  {% endif %}
</main>
