---
title: "Noh Lab - Pictures"
layout: piclay
excerpt: "Noh Lab -- Pictures"
permalink: /pictures/
---

# Pictures
<!--Jump to: [Leiden](#leiden), [ETHZ](#ethz), [Cornell](#cornell), [St Andrews](#st-andrews)


## Leiden
#### Timelapse of our STM assembling [(see LION news item)](https://www.physics.leidenuniv.nl/index.php?id=11573&news=867&type=lion&ln=EN):
<iframe width="560" height="315" src="https://www.youtube.com/embed/3iKvUMv1h5A" frameborder="0" allowfullscreen></iframe> -->
### Gallery
<!-- (Right-click *'view image'* to see a larger image.)-->
{% assign number_printed = 0 %}

<!-- for문 시작지점--> <!--for문을 pic세트 개수만큼 출력-->
{% for pic in site.data.pictures_gallery %} 
{% assign even_odd = number_printed | modulo: 4 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-3 clearfix">
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/Gallery/{{ pic.image }}" class="img-responsive" width="95%" style="float: left" />
