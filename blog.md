---
layout: page
title: Blog
permalink: /blog/
addthis: true
---

<div class="post-list">
  {% for post in site.posts %}
  <!-- Look the author details up from the site config. -->
  {% assign author = site.data.authors[post.author] %}

  <section class="section">
  <h2>
    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </h2>
  <h5>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span> <div class="addthis_toolbox addthis_default_style" addthis:url="{{ post.url | prepend: site.baseurl }}" addthis:title="{{ post.title}}" addthis:description="{% if post.excerpt %}{{ post.excerpt | strip_html | strip_newlines | truncate: 300 }}{% else %}{{ site.description }}{% endif %}">
  </h5>
  <p>
  {% if post.excerpt %}{{ post.excerpt | strip_html | strip_newlines | truncate: 300 }}{% else %}{{ site.description }}{% endif %}
  </p>
  </section>
  {% endfor %}
</div>
