---
layout: default
title: 首页
---

{% include nav.html %}

<section class="welcome">
  <h1 class="welcome-title">👋 欢迎来到我的小站</h1>
  <p class="welcome-desc">这里记录着我的学习笔记、生活感悟和一些有趣的折腾</p>
  <p class="welcome-meta">共 {{ site.posts | size }} 篇文章</p>
</section>

<section class="post-list">
  {% for post in site.posts limit:10 %}
  <article class="post-card">
    <div class="post-card-header">
      <time class="post-card-date" datetime="{{ post.date | date_to_xmlschema }}">
        <span class="date-day">{{ post.date | date: "%d" }}</span>
        <span class="date-month">{{ post.date | date: "%b" }}</span>
        <span class="date-year">{{ post.date | date: "%Y" }}</span>
      </time>
      <div class="post-card-info">
        <h2 class="post-card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <div class="post-card-meta">
          {% if post.categories.size > 0 %}
            {% for cat in post.categories %}
            <span class="tag tag-cat">{{ cat }}</span>
            {% endfor %}
          {% endif %}
          {% if post.tags.size > 0 %}
            {% for tag in post.tags %}
            <span class="tag tag-tag">{{ tag }}</span>
            {% endfor %}
          {% endif %}
        </div>
      </div>
    </div>
    <div class="post-card-body">
      {{ post.excerpt }}
    </div>
    <div class="post-card-footer">
      <a href="{{ post.url | relative_url }}" class="read-more">阅读全文 →</a>
    </div>
  </article>
  {% endfor %}
</section>
