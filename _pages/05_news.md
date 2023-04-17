---
layout: page
permalink: /news/
exclude: true
---

{% assign news = site.data.news | sort: 'date' %}

<p>X
{% for new in news reversed %}
  a <b>[{{ new.date }}]</b>{{ new.news }} c
{% endfor %}
Y
</p>
