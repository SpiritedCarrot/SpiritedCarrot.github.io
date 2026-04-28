---
layout: default
title: stuff i love
permalink: /stuff-i-love/
---

# stuff i love

A collection of links, references, and little sources of inspiration.

{% for group in site.data.stuff_i_love %}

## {{ group.category }}

{% for item in group.items %}
- [{{ item.name }}]({{ item.url }}){% if item.note %} — {{ item.note }}{% endif %}
{% endfor %}

{% endfor %}