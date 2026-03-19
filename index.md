---
layout: default
title: Home
---

<div class="post-list-header">
  <h1>Tech <span>Insights</span></h1>
  <p class="post-list-tagline">// code · tools · infrastructure · AI</p>
</div>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <a class="post-card" href="{{ post.url | prepend: site.baseurl }}">
        <div class="post-card-meta">
          <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
          {% if post.tags %}
            <div class="post-tags">
              {% for tag in post.tags %}
                <span class="post-tag">{{ tag }}</span>
              {% endfor %}
            </div>
          {% endif %}
        </div>
        <div class="post-card-title">{{ post.title }}</div>
        <div class="post-card-excerpt">{{ post.excerpt | strip_html | truncatewords: 22 }}</div>
        <span class="post-card-arrow">→</span>
      </a>
    </li>
  {% endfor %}
</ul>
