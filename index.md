---
layout: default
title: 首页
---

{% for post in site.posts limit:10 %}
- **{{ post.date | date: "%Y-%m-%d" }}** [{{ post.title }}]({{ post.url | relative_url }})
  {% if post.categories.size > 0 %}`{{ post.categories | join: "`, `" }}`{% endif %}
{% endfor %}
