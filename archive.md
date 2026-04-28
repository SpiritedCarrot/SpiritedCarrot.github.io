---
layout: default
title: archive
permalink: /archive/
---

# archive

{% assign items = site.posts | concat: site.comics | sort: "date" | reverse %}
{% assign current_year = "" %}

{% for item in items %}
{% assign year = item.date | date: "%Y" %}

{% if year != current_year %}
## {{ year }}
{% assign current_year = year %}
{% endif %}

{% assign label = item.type %}

{% if label == nil or label == "" %}
  {% if item.collection == "comics" %}
    {% assign label = "Comic" %}
  {% else %}
    {% assign label = "Note" %}
  {% endif %}
{% endif %}

<p>
  {{ item.date | date: "%b %-d" }} · {{ label }} ·
  <a href="{{ item.url | relative_url }}">
    {% if item.collection == "comics" and item.num %}
      #{{ item.num }} - {{ item.title | escape }}
    {% else %}
      {{ item.title | escape }}
    {% endif %}
  </a>
</p>
{% endfor %}