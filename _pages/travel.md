---
layout: page
title: Travel
permalink: /posts/categories/travel/
---

<style>
  .posts-grid {
    display: grid;
    gap: 2rem;
    margin-top: 2rem;
  }

  .post-card {
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    padding: 1.5rem;
    text-decoration: none;
    color: inherit;
    transition: all 0.3s ease;
  }

  .post-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);
  }

  .post-card h3 {
    margin: 0 0 0.5rem 0;
    color: #667eea;
  }

  .post-card small {
    color: #999;
  }

  .post-card p {
    margin: 0.5rem 0 0 0;
    color: #666;
    line-height: 1.6;
  }
</style>

# Travel Posts

Explore adventures and destinations from around the world.

<div class="posts-grid">
  {% for post in site.categories.travel %}
    <a href="{{ post.url }}" class="post-card">
      <h3>{{ post.title }}</h3>
      <small>{{ post.date | date: "%d %B %Y" }}</small>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </a>
  {% endfor %}
</div>
