---
layout: default
title: Tags
permalink: /tags/
---

<h1>Tags</h1>

{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  {% assign tagname = tag[0] %}
  {% assign slug = tagname | slugify %}
<h2 id="{{ slug }}">{{ tagname }}</h2>
<ul>
  {% for post in tag[1] %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <em>{{ post.date | date: "%-d %b %Y" }}</em></li>
  {% endfor %}
</ul>
{% endfor %}
