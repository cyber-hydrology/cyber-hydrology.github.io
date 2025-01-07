---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

**박사과정, 석사과정, 학부 연구생 모집합니다**<br>
**We are looking for new PhD, Master, Bachelor students to join the team** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**

<br>

## Principal Investigator
{% for member in site.data.team_professor %}
<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4 style="font-weight: bold;">{{ member.name }}</h4>
  <i>{{ member.info }}<br>email: <{{ member.email }}></i>
  <ul>
    {% for i in (1..member.number_educ) %}
      <li>{{ member["education" | append: i] }}</li>
    {% endfor %}
  </ul>
</div>
{% endfor %}

<br>

## PhD and Master Students
{% for member in site.data.team_students %}
  {% if forloop.index0 | modulo: 2 == 0 %}
  <div class="row">
  {% endif %}
    <div class="col-sm-6 clearfix">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
      <h4 style="font-weight: bold;">{{ member.name }}</h4>
      <i>{{ member.info }}<br>email: <{{ member.email }}></i>
      <ul>
        {% for i in (1..member.number_educ) %}
          <li>{{ member["education" | append: i] }}</li>
        {% endfor %}
      </ul>
    </div>
  {% if forloop.index | modulo: 2 == 0 or forloop.last %}
  </div>
  {% endif %}
{% endfor %}

<br>

## Undergraduate Students
{% for member in site.data.team_undergraduate_students %}
  {% if forloop.index0 | modulo: 2 == 0 %}
  <div class="row">
  {% endif %}
    <div class="col-sm-6 clearfix">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
      <h4 style="font-weight: bold;">{{ member.name }}</h4>
      <i>{{ member.info }}<br>email: <{{ member.email }}></i>
      <ul>
        {% for i in (1..member.number_educ) %}
          <li>{{ member["education" | append: i] }}</li>
        {% endfor %}
      </ul>
    </div>
  {% if forloop.index | modulo: 2 == 0 or forloop.last %}
  </div>
  {% endif %}
{% endfor %}

<br>

## Alumni Members
<div class="team-section">
{% for member in site.data.alumni_members %}
  <p><strong>{{ member.name }}</strong>: {{ member.info }}</p>
  <ul>
    {% for i in (1..member.number_educ) %}
      <li>{{ member["education" | append: i] }}</li>
    {% endfor %}
  </ul>
{% endfor %}
</div>
