---
layout: default
title: comics
permalink: /comics/
---

# comics

Small visual fragments and experiments.

{% assign comics = site.comics | sort: "date" | reverse %}

{% for comic in comics %}
<article class="feed-item">
  <div class="feed-label">
    Comic · {{ comic.date | date: "%b %-d, %Y" }}
  </div>

  <h2 class="feed-title">
    <a href="{{ comic.url | relative_url }}">
      {% if comic.num %}#{{ comic.num }} - {% endif %}{{ comic.title | escape }}
    </a>
  </h2>

  {% assign img = comic.strip_image | default: comic.image %}
  {% if img %}
    <a href="{{ comic.url | relative_url }}">
      <img class="feed-image" src="{{ img | relative_url }}" alt="{{ comic.alt | default: comic.title | escape }}">
    </a>
  {% endif %}

  {% if comic.caption %}
    <p>{{ comic.caption }}</p>
  {% endif %}
</article>
{% endfor %}