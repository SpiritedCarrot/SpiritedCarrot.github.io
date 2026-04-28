---
layout: default
title: bognik
---

## comics

<ul class="item-list">
  {% assign comics = site.comics | sort: "number" %}
  {% for comic in comics %}
    <li>
      <a href="{{ comic.url | relative_url }}">
        {% if comic.number %}{{ comic.number }} - {% endif %}{{ comic.title }}
      </a>
    </li>
  {% endfor %}
</ul>

## posts

<ul class="item-list">
  {% assign posts = site.posts | sort: "date" | reverse %}
  {% for post in posts %}
    <li>
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </li>
  {% endfor %}
</ul>