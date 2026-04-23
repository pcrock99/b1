---
layout: default
title: 标签
permalink: /tags/
---

# 🏷️ 文章标签

{% assign tags = site.tags | sort %}

{% for tag in tags %}
  <div style="margin-bottom: 30px;">
    <h2 id="{{ tag[0] | slugify }}" style="border-left: 4px solid var(--link-color); padding-left: 12px;">
      {{ tag[0] }} <span style="font-size: 0.8rem; color: #888;">({{ tag[1].size }} 篇)</span>
    </h2>
    <ul style="list-style: none; padding-left: 16px;">
      {% for post in tag[1] %}
        <li style="margin-bottom: 8px;">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <span style="font-size: 0.8rem; color: #888;">({{ post.date | date: "%Y-%m-%d" }})</span>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}

<hr style="border-color: var(--border-color); margin: 30px 0;">

<p style="text-align: center;">
  <a href="/bg/categories/" style="color: var(--link-color);">📂 查看分类</a> &nbsp;|&nbsp;
  <a href="/bg/" style="color: var(--link-color);">🏠 返回首页</a>
</p>