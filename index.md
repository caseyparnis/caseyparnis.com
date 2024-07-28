---
layout: default
title: Home
---

<div class="home">

  {% if site.posts.size > 0 %}
    <h2>Recent Posts</h2>
    <ul class="post-list">
      {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
      {% for post in site.posts limit:5 %}
        <li>
          <span class="post-meta">{{ post.date | date: date_format }}</span>
          <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
              {{ post.title | escape }}
            </a>
          </h3>
          {% if post.excerpt %}
            <p>{{ post.excerpt | strip_html }}</p>
          {% else %}
            <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
          {% endif %}
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <p>No posts available.</p>
  {% endif %}
</div>