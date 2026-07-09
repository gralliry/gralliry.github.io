---
layout: default
title: 首页
---

{% include nav.html %}

{% for post in site.posts limit:10 %}
<article class="post-card">
  <div class="post-card-header">
    <h2 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <span class="card-date">{{ post.date | date: "%Y-%m-%d" }}</span>
  </div>
  <div class="card-meta">
    {% if post.categories.size > 0 %}
    {% for cat in post.categories %}
    <span class="tag">#{{ cat }}</span>
    {% endfor %}
    {% endif %}
    {% if post.tags.size > 0 %}
    {% for tag in post.tags %}
    <span class="tag">#{{ tag }}</span>
    {% endfor %}
    {% endif %}
  </div>
</article>
{% endfor %}
