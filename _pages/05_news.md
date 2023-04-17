---
layout: page
title: News
permalink: /news/
---

{% assign news = site.data.news | sort: 'date' | group_by: 'year' %}

<p>
{% for new in news reversed %}
  <b>[{{ new.date }}]</b>{{ new.news }}
{% endfor %}
</p>
