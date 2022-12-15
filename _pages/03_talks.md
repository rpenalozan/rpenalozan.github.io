---
layout: page
title: Talks
permalink: /talks/
---

<div id='keynotes'>

<h3> Keynotes </h3>

{% assign talks = site.data.talks.keynote | sort: 'date' | reverse %}

{% for talk in talks %}

  <p>
  <b>[{{ talk.date | date: "%b %d, %Y" }}]</b> <i>{{ talk.title }}</i> at the {{ talk.venue }};
	{{ talk.location }}
  </p>

{% endfor %}

</div>

<div id='talks'>

<h3> Invited Talks </h3>

{% assign talks = site.data.talks.talk | sort: 'date' | reverse %}

{% for talk in talks %}

  <p>
  <b>[{{ talk.date | date: "%b %d, %Y" }}]</b> <i>{{ talk.title }}</i> at the {{ talk.venue }};
	{{ talk.location }}&nbsp;
	{% if talk.url %}
	|&nbsp;<a href="{{ talk.url }}">Recording</a>&nbsp;
	{% endif %}
	{% if talk.note %}
		|&nbsp;<b>({{ talk.note }})</b>
	{% endif %}
  </p>

{% endfor %}

</div>

<div id='tutorials'>

<h3> Tutorials </h3>

{% assign talks = site.data.talks.tutorial | sort: 'date' | reverse %}

{% for talk in talks %}

  <p>
  <b>[{{ talk.date | date: "%b %d, %Y" }}{% if talk.end %}-{{ talk.end | date: "%b %d, %Y" }}{% endif %}]</b> <i>{{ talk.title }}</i> at the {{ talk.venue }};
	{{ talk.location }}
	{% if talk.note %}
		|&nbsp;<b>({{ talk.note }})</b>
	{% endif %}
  </p>

{% endfor %}

</div>
