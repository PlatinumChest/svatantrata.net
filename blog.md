---
layout: page
title: Blog
permalink: /blog/
---

{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

<ul class="post-list">
{% for post in posts %}
  <li>
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  </li>
{% endfor %}
</ul>

{% if paginator %}
<nav class="pager">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&larr; Newer</a>
  {% endif %}
  {% if paginator.next_page %}
    <a style="float:right" href="{{ paginator.next_page_path | relative_url }}">Older &rarr;</a>
  {% endif %}
</nav>
{% endif %}
