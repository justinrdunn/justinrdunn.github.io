---
layout: post
title: Blog
permalink: /blog/
---

<ul class="blog">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}"><h4>{{ post.title }}</h4></a>
        <p class="meta">{{ post.date | date: '%B %d, %Y' }} by Justin Dunn</p>
      <hr>
      {% if post.image %}
      <div class="blog-img" style="background-image: url({{ site.url }}/images/{{ post.image }});"></div>
      {% endif %}
      {{ post.content | strip_html | truncatewords: 50 }}
    </li>
  {% endfor %}
</ul>
