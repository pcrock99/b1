---
layout: default
title: 首页
---

# 我的博客

## 最新文章

<ul>
  {% for post in site.posts %}
    <li>
      <a href="/bg{{ post.url }}">{{ post.title }}</a>
      <span style="color:#666; font-size:0.9rem;">({{ post.date | date: "%Y-%m-%d" }})</span>
    </li>
  {% endfor %}
</ul>