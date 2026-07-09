---
layout: default
title: 首页
---

{% include nav.html %}

<section class="posts">
  {% for post in site.posts limit:10 %}
  <article class="post-card">
    <div class="card-left">
      <time class="card-date">{{ post.date | date: "%Y-%m-%d" }}</time>
      <div class="card-meta">
        {% if post.categories.size > 0 %}
        {% for cat in post.categories %}
        <span class="tag">{{ cat }}</span>
        {% endfor %}
        {% endif %}
        {% if post.tags.size > 0 %}
        {% for tag in post.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
        {% endif %}
      </div>
    </div>
    <div class="card-right">
      <h2 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <div class="card-excerpt">{{ post.excerpt }}</div>
    </div>
  </article>
  {% endfor %}
</section>
