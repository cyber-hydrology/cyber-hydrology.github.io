---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

## Principal Investigator

{% assign number_printed = 0 %}
{% for member in site.data.team_professor %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
{% endif %}

#### {{ member.name }}

{{ member.info }}
email: <{{ member.email }}>

{% if member.number_educ == 1 %}
  * {{ member.education1 }}
{% endif %}
{% if member.number_educ == 2 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
{% endif %}
{% if member.number_educ == 3 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
{% endif %}
{% if member.number_educ == 4 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
{% endif %}
{% if member.number_educ == 5 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
  * {{ member.education5 }}
{% endif %}

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
{% endif %}
{% endfor %}

## POST DOC

{% assign number_printed = 0 %}
{% for member in site.data.team_postdoc %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
{% endif %}

#### {{ member.name }}

{{ member.info }}
email: <{{ member.email }}>

{% if member.number_educ == 1 %}
  * {{ member.education1 }}
{% endif %}
{% if member.number_educ == 2 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
{% endif %}
{% if member.number_educ == 3 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
{% endif %}
{% if member.number_educ == 4 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
{% endif %}
{% if member.number_educ == 5 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
  * {{ member.education5 }}
{% endif %}

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
{% endif %}
{% endfor %}

## PhD and Master Students

{% assign number_printed = 0 %}
{% for member in site.data.team_students %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
{% endif %}

#### {{ member.name }}

{{ member.info }}
email: <{{ member.email }}>

{% if member.number_educ == 1 %}
  * {{ member.education1 }}
{% endif %}
{% if member.number_educ == 2 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
{% endif %}
{% if member.number_educ == 3 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
{% endif %}
{% if member.number_educ == 4 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
{% endif %}
{% if member.number_educ == 5 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
  * {{ member.education5 }}
{% endif %}

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
{% endif %}
{% endfor %}

## Undergraduate Students

{% assign number_printed = 0 %}
{% for member in site.data.team_undergraduate_students %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
{% endif %}

#### {{ member.name }}

{{ member.info }}
email: <{{ member.email }}>

{% if member.number_educ == 1 %}
  * {{ member.education1 }}
{% endif %}
{% if member.number_educ == 2 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
{% endif %}
{% if member.number_educ == 3 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
{% endif %}
{% if member.number_educ == 4 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
{% endif %}
{% if member.number_educ == 5 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
  * {{ member.education5 }}
{% endif %}

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
{% endif %}
{% endfor %}

## Alumni Members

{% assign number_printed = 0 %}
{% for member in site.data.alumni_members %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
{% endif %}

#### {{ member.name }}

{{ member.info }}
email: <{{ member.email }}>

{% if member.number_educ == 1 %}
  * {{ member.education1 }}
{% endif %}
{% if member.number_educ == 2 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
{% endif %}
{% if member.number_educ == 3 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
{% endif %}
{% if member.number_educ == 4 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
{% endif %}
{% if member.number_educ == 5 %}
  * {{ member.education1 }}
  * {{ member.education2 }}
  * {{ member.education3 }}
  * {{ member.education4 }}
  * {{ member.education5 }}
{% endif %}

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
{% endif %}
{% endfor %}
