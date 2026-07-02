---
title: "Noh Lab - Presentations (Archive)"
layout: gridlay
excerpt: "Noh Lab -- Presentations archive (2021-2024)."
sitemap: false
permalink: /presentations/archive/
---

# Presentations &mdash; Archive

## Posters (2021&ndash;2024)

<p><a href="{{ site.url }}{{ site.baseurl }}/presentations/"><strong>&larr; Back to recent posters (2025&ndash;2026)</strong></a><br/>
<em>Click any poster to open the full-resolution image.</em></p>

{% assign number_printed = 0 %}
{% for poster in site.data.posters %}

{% if poster.highlight == 1 and poster.year <= 2024 %}
{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}
 
<div class="col-sm-6 clearfix">
  <div class="well flex-design shadow-none">
  <protit>{{ poster.title }}</protit>
  <div>
  <a href="{{ site.url }}{{ site.baseurl }}/images/propic/{{ poster.image }}" target="_blank" rel="noopener">
  <img src="{{ site.url }}{{ site.baseurl }}/images/propic/thumbs/{{ poster.image }}" class="img-responsive" width="33%" style="float: left" loading="lazy" alt="{{ poster.title }}" />
  </a>
  <p>{{ poster.description }}</p>
  <p><em>{{ poster.authors }}</em></p>
  </div>
  <p><strong><a href="{{ poster.link.url }}">{{ poster.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ poster.news1 }}</strong></p>
  <p> {{ poster.news2 }}</p>
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

<p>&nbsp;</p>
<p><a href="{{ site.url }}{{ site.baseurl }}/presentations/"><strong>&larr; Back to recent posters (2025&ndash;2026)</strong></a></p>
