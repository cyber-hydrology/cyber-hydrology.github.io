---
title: "Noh Lab - Pictures"
layout: piclay
excerpt: "Noh Lab -- Pictures"
permalink: /pictures/
---

# Pictures

### Gallery

{% assign number_printed = 0 %}

{% for pic in site.data.pictures_gallery %}
  {% assign even_odd = number_printed | modulo: 4 %}

  {% if even_odd == 0 %}
  <div class="row">
  {% endif %}

  <div class="col-sm-3 clearfix">
    <img src="{{ site.url }}{{ site.baseurl }}/images/picpic/Gallery/{{ pic.image }}" class="img-responsive" width="95%" style="float: left" />
    <p>{{ pic.caption }}</p>
  </div>

  {% assign number_printed = number_printed | plus: 1 %}

  {% if even_odd == 3 %}
  </div>
  {% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 4 %}
{% if even_odd != 0 %}
</div>
{% endif %}
