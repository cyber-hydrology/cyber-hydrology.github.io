---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

<div id="gridid" class="col-sm-12">

# Group Members

{% assign groups = "Principal Investigator:team_professor,POST DOC:team_postdoc,PhD and Master Students:team_students,Undergraduate Students:team_undergraduate_students,Alumni Members:alumni_members" | split: "," %}

{% for group in groups %}
{% assign group_info = group | strip | split: ":" %}
{% assign group_title = group_info[0] %}
{% assign group_data = group_info[1] %}

## {{ group_title }}

{% if group_data == "team_professor" %}

<div class="professor-section">
{% for member in site.data[group_data] %}
<div class="professor-card">

{% if member.photo %}
<div class="professor-photo-box">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="professor-photo" alt="{{ member.name }}">
</div>
{% endif %}

<div class="professor-info-box">

<h3>{{ member.name }}</h3>

{% if member.info %}
<p>{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p>Email: {{ member.email }}</p>
{% endif %}

{% if member.education1 %}
<ul class="professor-list">
<li>{{ member.education1 }}</li>
{% if member.education2 %}
<li>{{ member.education2 }}</li>
{% endif %}
{% if member.education3 %}
<li>{{ member.education3 }}</li>
{% endif %}
{% if member.education4 %}
<li>{{ member.education4 }}</li>
{% endif %}
{% if member.education5 %}
<li>{{ member.education5 }}</li>
{% endif %}
</ul>
{% endif %}

{% if member.appointment_items %}
<h5>{{ member.appointment_title | default: "Appointments" }}</h5>
<ul class="professor-list">
{% for item in member.appointment_items %}
<li>{{ item.text }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.research_items %}
<h5>{{ member.research_title | default: "Research Interests" }}</h5>
<ul class="professor-list">
{% for item in member.research_items %}
<li>{{ item.text }}</li>
{% endfor %}
</ul>
{% endif %}

</div>

</div>
{% endfor %}
</div>

{% else %}

{% assign number_printed = 0 %}

{% for member in site.data[group_data] %}
{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">

{% if member.photo %}
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left; margin-right: 15px;" />
{% endif %}

{% assign has_pubs = false %}
{% if member.intl_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.intl_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_items %}{% assign has_pubs = true %}{% endif %}

{% if has_pubs %}
<details class="member-toggle">
<summary><strong>{{ member.name }}</strong></summary>
{% else %}
<h3>{{ member.name }}</h3>
{% endif %}

{% if member.info %}
<p>{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p>Email: {{ member.email }}</p>
{% endif %}

{% if member.education1 or member.education2 or member.education3 or member.education4 or member.education5 %}
<ul>
{% if member.education1 %}
<li>{{ member.education1 }}</li>
{% endif %}
{% if member.education2 %}
<li>{{ member.education2 }}</li>
{% endif %}
{% if member.education3 %}
<li>{{ member.education3 }}</li>
{% endif %}
{% if member.education4 %}
<li>{{ member.education4 }}</li>
{% endif %}
{% if member.education5 %}
<li>{{ member.education5 }}</li>
{% endif %}
</ul>
{% endif %}

{% if member.research %}
<ul>
{% for item in member.research %}
<li>{{ item }}</li>
{% endfor %}
</ul>
{% endif %}

{% if has_pubs %}

{% if member.intl_journal_items %}
<h5>{{ member.intl_journal_title | default: "International Journal Papers" }}</h5>
<ul>
{% for pub in member.intl_journal_items %}
<li>{{ pub.text }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.domestic_journal_items %}
<h5>{{ member.domestic_journal_title | default: "Domestic Journal Papers" }}</h5>
<ul>
{% for pub in member.domestic_journal_items %}
<li>{{ pub.text }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.intl_items %}
<h5>{{ member.intl_title | default: "International Conference Papers" }}</h5>
<ul>
{% for pub in member.intl_items %}
<li>{{ pub.text }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.domestic_items %}
<h5>{{ member.domestic_title | default: "Domestic Conference Papers" }}</h5>
<ul>
{% for pub in member.domestic_items %}
<li>{{ pub.text }}</li>
{% endfor %}
</ul>
{% endif %}

</details>
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

{% endif %}

{% endfor %}

</div>
