---
title: "Noh Lab - Presentations"
layout: gridlay
excerpt: "Noh Lab -- Presentations."
sitemap: false
permalink: /presentations/
---

# Presentations

## Posters

<!-- (For a full list see [below](#full-list) or go to [Google Scholar](https://scholar.google.com/citations?user=Q0Z_uB8AAAAJ&hl=en), [ResearcherID](https://publons.com/researcher/1296422/seong-jin-noh/)) -->

{% assign number_printed = 0 %}
{% for poster in paginator.posts %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if poster.highlight == 1 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}
 
<div class="col-sm-6 clearfix">
  <div class="well flex-design shadow-none">
  <protit>{{ poster.title }}</protit>
  <div>
  <img src="{{ site.url }}{{ site.baseurl }}/images/propic/{{ poster.image }}" class="img-responsive" width="33%" style="float: left" />
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

{% if paginator.total_pages > 1 %}
<div class="pagination">
{% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Prev</a>
{% else %}
    <span>&laquo; Prev</span>
{% endif %}

{% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
    <em>{{ page }}</em>
    {% elsif page == 1 %}
    <a href="{{ '/' | relative_url }}">{{ page }}</a>
    {% else %}
    <a href="{{ site.paginate_path | relative_url | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
{% endfor %}

{% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}">Next &raquo;</a>
{% else %}
    <span>Next &raquo;</span>
{% endif %}
</div>
{% endif %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}

<p> &nbsp; </p>
