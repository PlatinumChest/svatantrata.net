---
layout: page
title: Blog
permalink: /blog/
---

<ul class="post-list">
{% for post in paginator.posts %}
  <li>
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  </li>
{% endfor %}
</ul>

<div class="pager">
{% if paginator.previous_page %}
  <a href="{{ paginator.previous_page_path | relative_url }}">&larr; Newer</a>
{% endif %}
{% if paginator.next_page %}
  <a style="float:right" href="{{ paginator.next_page_path | relative_url }}">Older &rarr;</a>
{% endif %}
</div>
