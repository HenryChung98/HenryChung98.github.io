---
layout: default
title: Apps
---
# {{ site.title }}

{{ site.description }}

<ul class="cards">
{% assign apps = site.apps | where: "layout", "app" | sort: "title" %}
{% for app in apps %}
  <li><a href="{{ app.url | relative_url }}">{{ app.title }}{% if app.description %}<span class="muted">{{ app.description }}</span>{% endif %}</a></li>
{% endfor %}
</ul>
