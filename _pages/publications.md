---
title: "Noh Lab - Publications"
layout: gridlay
excerpt: "Noh Lab -- Publications."
sitemap: false
permalink: /publications/
---


<!-- # Publications
## Highlights
(For a full list see [below](#full-list) or go to [Google Scholar](https://scholar.google.com/citations?user=Q0Z_uB8AAAAJ&hl=en), [ResearcherID](https://publons.com/researcher/1296422/seong-jin-noh/))
To be updated soon..
{% assign number_printed = 0 %}
{% for publi in site.data.publist %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}
{% if even_odd == 0 %}
<div class="row">
{% endif %}
<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
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
<p> &nbsp; </p> -->


<!-- ## Full List -->
{% for year in (2015..2022) reversed %}
  <h3 style="font-size: 35px;">{{ year }}</h3>
  
  {% for publi in site.data.publist %}
   {% if publi.year == year %}
   <p style="font-size: 18px;">
    {{ publi.title }} <br />
    <em>{{ publi.authors }} </em> <br />
    <a href="{{ publi.link.url }}">{{ publi.link.display }}</a>
   </p>
   {% endif %}
  {% endfor %}
  
 {% endfor %}





