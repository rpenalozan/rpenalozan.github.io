---
layout: page
title: Publications
permalink: /pubs/
---

{% assign year_grouped = site.data.pubs | sort: 'year' | group_by: 'year' %}

I have {{ site.data.pubs.size }} publications in different venues. Below you can find
all relevant bibliographic information, including Bibtex, DOI, and (in some cases) a
preprint version of the paper. Preprints for older papers (before 2015) are available
at the [LAT Webpage](https://tu-dresden.de/ing/informatik/thi/lat/forschung/veroeffentlichungen).

<p>
{% for group in year_grouped reversed %}
  <a href="#{{ group.name }}">{{ group.name }}</a>&nbsp;
{% endfor %}
</p>
<div id='bib'>
{% for group in year_grouped reversed %}
  <h3 id="{{ group.name }}">{{ group.name }}</h3>
  <ul>
{% assign papers = group.items | sort: 'type' %}
{% for paper in papers reversed %}
  <li id="{{ paper.key }}">
    {{ paper.author }}. <span class="pub-title">{{ paper.title }}</span>. {% if paper.venue %} In {{ paper.venue }} {% endif %} {% if paper.type==2 %} [Thesis] {% endif %} <br />
    <a href="#a{{ paper.key }}">BibTex</a>&nbsp;
    {% if paper.doi %}
    <a href="http://dx.doi.org/{{ paper.doi }}">DOI</a>&nbsp;
    {% endif %}
    {% assign pdfs = site.static_files | where: "paper", true | where: "basename", paper.key | first %}
    {% if pdfs %}
    <a href="{{ paper.key | prepend: "papers/" | relative_url }}.pdf">PDF</a>&nbsp;
    {% endif %}
    {% if paper.arxiv %}
    <a href="{{ paper.arxiv }}">arXiv</a>&nbsp;
    {% endif %}
    <pre id='a{{ paper.key }}' class='bib'>{{ paper.bib }}</pre>
  </li>
{% endfor %}
  </ul>
{% endfor %}
</div>

