---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

<div id="gridid" class="col-sm-12">

# Group Members

{% assign groups = "Principal Investigator:team_professor, POST DOC:team_postdoc, PhD and Master Students:team_students, Undergraduate Students:team_undergraduate_students, Alumni Members:alumni_members" | split: "," %}

{% for group in groups %}
{% assign group_info = group | strip | split: ":" %}
{% assign group_title = group_info[0] %}
{% assign group_data = group_info[1] %}

## {{ group_title }}

{% assign number_printed = 0 %}

{% for member in site.data[group_data] %}
{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">

{% if member.photo %}
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
{% endif %}

### {{ member.name }}

{% if member.info %}
{{ member.info }}
{% endif %}

{% if member.email %}
Email: <{{ member.email }}>
{% endif %}

{% if member.education1 %}
- {{ member.education1 }}
{% endif %}
{% if member.education2 %}
- {{ member.education2 }}
{% endif %}
{% if member.education3 %}
- {{ member.education3 }}
{% endif %}
{% if member.education4 %}
- {{ member.education4 }}
{% endif %}
{% if member.education5 %}
- {{ member.education5 }}
{% endif %}

{% if member.research %}
{% for item in member.research limit:2 %}
- {{ item }}
{% endfor %}
{% endif %}

</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

</div>
