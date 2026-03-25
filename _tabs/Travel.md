---
layout: page
title: Travel
icon: fas fa-plane
permalink: /travel/
order: 1
---

{% for post in site.categories.Travel %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
