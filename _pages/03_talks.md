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
  <b>[{{ talk.date | date: "%b %d, %Y" }}]</b> <i>{{ talk.title }}</i> at the {{ talk.venue }}
  </p>

{% endfor %}

</div>

<div id='tutorials'>

<h3> Tutorials </h3>

{% assign talks = site.data.talks.tutorial | sort: 'date' | reverse %}

{% for talk in talks %}

  <p>
  <b>[{{ talk.date | date: "%b %d, %Y" }}]</b> <i>{{ talk.title }}</i> at the {{ talk.venue }}
  </p>

{% endfor %}

</div>
