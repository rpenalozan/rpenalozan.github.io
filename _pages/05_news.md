---
layout: page
permalink: /news/
exclude: true
---

<h1> News </h1>

{% assign news = site.data.news | sort: 'date' %}

<p>
{% for new in news reversed %}
  <b>[{{ new.date }}]</b> {{ new.news }}
  {% if new.url %}
  (<a href="{{ new.url }}">{{ new.url }}</a>)
  {% endif %}
  <br />
{% endfor %}
</p>
