---
layout: default
title: Archive
permalink: /archive/
---

<h1>📅 Archive</h1>

{% assign entries = site.pages | where_exp: "item", "item.url contains '/archive/'" %}

<ul class="archive-list">
  {% for entry in entries reversed %}
  <li>
    <a href="{{ entry.url | relative_url }}">{{ entry.url | remove: '/archive/' | remove: '.html' | date: "%A, %B %-d, %Y" }}</a>
  </li>
  {% endfor %}
</ul>

{% assign entries_len = entries | size %}
{% if entries_len == 0 %}
<div class="empty-state">
  <h2>No archived digests yet 📭</h2>
  <p>Daily digests will appear here after each trading day.</p>
</div>
{% endif %}
