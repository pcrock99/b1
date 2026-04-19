---
layout: default
title: 分类
permalink: /categories/
---

# 📂 所有分类

{% assign categories = site.categories | sort %}

<ul>
  {% for category in categories %}
    <li>
      <strong>{{ category[0] }}</strong> （{{ category[1].size }} 篇文章）
      <ul>
        {% for post in category[1] %}
          <li>
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <span style="color:#666; font-size:0.8rem;">（{{ post.date | date: "%Y-%m-%d" }}）</span>
          </li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>