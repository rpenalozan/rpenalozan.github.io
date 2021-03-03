---
layout: page
title: Research
permalink: /research/
---

<h3>PC Memberships</h3>

<div id='pc'>
{% assign year_grouped = site.data.pc | sort: 'year' | reverse %}

{% for group in year_grouped limit:2 %}
  <h3 id="{{ group.year }}">{{ group.year }}</h3>
  <ul>
{% assign venues = group.venues | sort: 'note' | reverse %}
{% for venue in venues %}
  <li>
    {% if venue.url %}
    <a href="{{ venue.url }}">{{ venue.name }}</a>
    {% else %}
    {{ venue.name }}
    {% endif %}
    {% if venue.note %}
    [<span class="pub-title">{{ venue.note }}</span>]
    {% endif %}
  </li>
{% endfor %}
  </ul>
{% endfor %}
<a href='#old' id='show'>Show older</a>
<div id='old' class='hide'>
<a href='#show'>Hide</a>
{% for group in year_grouped offset:2 %}
  <h3 id="{{ group.year }}">{{ group.year }}</h3>
  <ul>
{% assign venues = group.venues %}
{% for venue in venues %}
  <li>
    {{ venue.name }}
    {% if venue.note %}
    [<span class="pub-title">{{ venue.note }}</span>]
    {% endif %}
  </li>
{% endfor %}
  </ul>
{% endfor %}
</div>
</div>
{% comment %}
{% endcomment %}
