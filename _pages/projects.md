---
title: "Noh Lab - Projects"
layout: gridlay
excerpt: "Noh Lab -- Projects."
sitemap: false
permalink: /projects/
---

# Projects

## Posters

<!-- (For a full list see [below](#full-list) or go to [Google Scholar](https://scholar.google.com/citations?user=Q0Z_uB8AAAAJ&hl=en), [ResearcherID](https://publons.com/researcher/1296422/seong-jin-noh/)) -->

{% assign number_printed = 0 %}
{% for project in site.data.projects %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if project.highlight == 1 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}
 
<div class="col-sm-6 clearfix">
 <div class="well fixedHeight">
  <protit>{{ project.title }}</protit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/propic/{{ project.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ project.description }}</p>
  <p><em>{{ project.authors }}</em></p>
  <p><strong><a href="{{ project.link.url }}">{{ project.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ project.news1 }}</strong></p>
  <p> {{ project.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}

</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}

<p> &nbsp; </p>
