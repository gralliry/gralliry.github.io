---
layout: default
title: 首页
---

{% assign post_count = site.posts | size %}
{% if post_count == 0 %}
  <p>暂无文章</p>
{% else %}
  {% for post in site.posts limit:10 %}
    <article style="margin-bottom: 2rem; border-bottom: 1px solid #e8e8e8; padding-bottom: 1.5rem;">
      <h2 style="margin-bottom: 0.3rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: #0366d6;">{{ post.title }}</a>
      </h2>
      <p style="color: #828282; font-size: 0.85rem; margin-bottom: 0.8rem;">
        {{ post.date | date: "%Y-%m-%d" }}
        {% if post.categories and post.categories.size > 0 %}
          &nbsp;|&nbsp;
          {% for cat in post.categories %}
            <span style="background: #f1f8ff; padding: 0.1rem 0.4rem; border-radius: 3px; font-size: 0.8rem;">{{ cat }}</span>
          {% endfor %}
        {% endif %}
        {% if post.tags and post.tags.size > 0 %}
          {% for tag in post.tags %}
            <span style="background: #f0f0f0; padding: 0.1rem 0.4rem; border-radius: 3px; font-size: 0.8rem;">{{ tag }}</span>
          {% endfor %}
        {% endif %}
      </p>
      {{ post.excerpt }}
      <p><a href="{{ post.url | relative_url }}" style="font-size: 0.9rem;">阅读全文 →</a></p>
    </article>
  {% endfor %}
{% endif %}
