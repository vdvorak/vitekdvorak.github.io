---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<ul class="nolist">
  {% for post in site.posts %}
    <li>
      <div><a href="{{ post.url }}">{{post.date | date: "%Y-%m-%d "}} {{ post.title }}</a></div>
    </li>
  {% endfor %}
</ul>
