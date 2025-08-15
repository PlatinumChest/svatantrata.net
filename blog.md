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
  {% include post_card.html
     title=post.title
     url=post.url
     date=post.date
     excerpt=post.excerpt %}
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
