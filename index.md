---
layout: default
title: 首页
---

{% for post in site.posts limit:10 %}
<article class="post-item">
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p class="post-meta">
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
    {% if post.categories.size > 0 %}
    {% for cat in post.categories %}
    <span class="post-category">{{ cat }}</span>
    {% endfor %}
    {% endif %}
    {% if post.tags.size > 0 %}
    {% for tag in post.tags %}
    <span class="post-tag">{{ tag }}</span>
    {% endfor %}
    {% endif %}
  </p>
  {{ post.excerpt }}
  <p><a href="{{ post.url | relative_url }}" class="read-more">阅读全文 →</a></p>
</article>
{% endfor %}
