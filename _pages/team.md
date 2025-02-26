---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

<br>
## Principal Investigator
{% assign number_printed = 0 %}
{% for member in site.data.team_professor %}

{% if number_printed | modulo: 2 == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 d-flex align-items-center">
  <img src="{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="margin-right: 10px;" alt="{{ member.name }}" />
  <div>
    <h4 style="font-weight: bold;">{{ member.name }}</h4>
    <i>{{ member.info }}<br>Email: <a href="mailto:{{ member.email }}">{{ member.email }}</a></i>
    <ul>
      {% for i in (1..member.number_educ) %}
        <li>{{ member["education" | append: i] }}</li>
      {% endfor %}
    </ul>
  </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if number_printed | modulo: 2 == 0 %}
</div>
{% endif %}

{% endfor %}
{% if number_printed | modulo: 2 == 1 %}</div>{% endif %}

<br>
## PhD and Master Students
{% assign number_printed = 0 %}
{% for member in site.data.team_students %}

{% if number_printed | modulo: 2 == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4 style="font-weight: bold;">{{ member.name }}</h4>
  <i>{{ member.info }}<br>email: <{{ member.email }}></i>
  <ul style="overflow: hidden">
    {% for i in (1..member.number_educ) %}
      <li>{{ member["education" | append: i] }}</li>
    {% endfor %}
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if number_printed | modulo: 2 == 0 %}
</div>
{% endif %}

{% endfor %}
{% if number_printed | modulo: 2 == 1 %}</div>{% endif %}

<br>
## Undergraduate Students
{% assign number_printed = 0 %}
{% for member in site.data.team_undergraduate_students %}

{% if number_printed | modulo: 2 == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4 style="font-weight: bold;">{{ member.name }}</h4>
  <i>{{ member.info }}<br>email: <{{ member.email }}></i>
  <ul style="overflow: hidden">
    {% for i in (1..member.number_educ) %}
      <li>{{ member["education" | append: i] }}</li>
    {% endfor %}
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if number_printed | modulo: 2 == 0 %}
</div>
{% endif %}

{% endfor %}
{% if number_printed | modulo: 2 == 1 %}</div>{% endif %}

<br>
## Alumni Members
<ul>
{% for member in site.data.alumni_members %}
  <li><strong>{{ member.name }}</strong> - {{ member.info }}
    <ul>
      {% for i in (1..member.number_educ) %}
        <li>{{ member["education" | append: i] }}</li>
      {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>

