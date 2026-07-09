---
layout: default
title: 首页
---

{% include nav.html %}

{% for post in site.posts limit:10 %}
<article class="post-line">
  <time>{{ post.date | date: "%Y-%m-%d" }}</time>
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <div class="post-line-meta">
    {% if post.categories.size > 0 %}
    {% for cat in post.categories %}
    <span>{{ cat }}</span>
    {% endfor %}
    {% endif %}
    {% if post.tags.size > 0 %}
    {% for tag in post.tags %}
    <span>{{ tag }}</span>
    {% endfor %}
    {% endif %}
  </div>
</article>
{% endfor %}
