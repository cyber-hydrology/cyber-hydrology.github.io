
<!-- for문 시작지점--> <!--for문을 pic세트 개수만큼 출력-->
{% for pic in site.data.pictures_gallery %} 
{% assign even_odd = number_printed | modulo: 4 %}
{% if even_odd == 0 %}
<div class="row">
{% endif %}
<div class="col-sm-3 clearfix">
<img src="{{ site.url }}{{ site.baseurl }}/images/picpic/Gallery/{{ pic.image }}" class="img-responsive" width="95%" style="float: left" />
</div>
{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd > 2 %}
</div>
{% endif %}

{% endfor %}
<!-- for문 끝나는 지점 -->

{% assign even_odd = number_printed | modulo: 4 %}
