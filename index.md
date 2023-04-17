---
layout: home
---

<img src="{{ "/img/rpn.jpg" | prepend: site.baseurl }}" width="300px">

<p> I am an Associate Professor at the <a href="http://www.ir.disco.unimib.it/">
IKR3 Lab</a> of the <a href="https://en.unimib.it/">University of Milano-Bicocca</a>. </p>

<p> My main interests are in Knowledge Representation. I devise techniques
for solving non-standard reasoning problems, and extend knowledge 
representation formalisms (in particular Description Logics) to handle 
meta-knowledge. I like to explore new challenges, and have worked in
many different topics.</p>

<p> My latest interest is in the representation and use of uncertainty in knowledge </p>

<p> This page is constantly being updated </p>

<p> <b>News</b> <br />
{% assign news = site.data.news | sort: 'date' %}
{% for new in news reversed limit:3 %}
  <b>[{{ new.date }}]</b> {{ new.news }}
  {% if new.url %}
  (<a href="{{ new.url }}">{{ new.url }}</a>)
  {% endif %}
{% endfor %}
<br />
<a href="/news/">Older news</a>
</p>
