---
layout: page
permalink: /news/
exclude: true
---

{% assign news = site.data.news | sort: 'date' %}

<p>
{% for new in news reversed %}
  <b>[{{ new.date }}]</b> {{ new.news }}
  {% if new.url %}
  (<a href="{{ new.url }}">{{ new.url }}</a>)
  {% endif %}
{% endfor %}
</p>
