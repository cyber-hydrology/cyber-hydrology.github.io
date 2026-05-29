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

{% assign number_printed = 0 %}

{% for member in site.data[group_data] %}
{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6">
<div class="memberbox">

<div class="member-photo-box">
{% if member.photo %}
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive member-photo" />
{% endif %}
</div>

<div class="member-info-box">

{% assign has_pubs = false %}
{% if member.intl_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.intl_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_items %}{% assign has_pubs = true %}{% endif %}

{% if has_pubs %}
<h3 class="member-toggle-name" onclick="toggleMemberDetail(this)">{{ member.name }} <span class="toggle-arrow">▾</span></h3>
{% else %}
<h3>{{ member.name }}</h3>
{% endif %}

{% if member.info %}
<p>{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p>Email: <a href="mailto:{{ member.email }}">{{ member.email }}</a></p>
{% endif %}

<ul>
{% if member.education1 %}<li>{{ member.education1 }}</li>{% endif %}
{% if member.education2 %}<li>{{ member.education2 }}</li>{% endif %}
{% if member.education3 %}<li>{{ member.education3 }}</li>{% endif %}
{% if member.education4 %}<li>{{ member.education4 }}</li>{% endif %}
{% if member.education5 %}<li>{{ member.education5 }}</li>{% endif %}
{% if member.research %}
{% for item in member.research %}
<li>{{ item }}</li>
{% endfor %}
{% endif %}
</ul>

</div>
</div>

{% if has_pubs %}
<div class="member-detail-panel">

{% if member.intl_journal_items %}
<div class="pub-section">
<h5>{{ member.intl_journal_title | default: "International Journal Papers" }}</h5>
<ul>
{% for pub in member.intl_journal_items %}
<li data-url="{% if pub.url %}{{ pub.url }}{% endif %}" {% if pub.url %}onclick="window.open(this.dataset.url,'_blank')" style="cursor:pointer"{% endif %}>{{ pub.text | markdownify }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.domestic_journal_items %}
<div class="pub-section">
<h5>{{ member.domestic_journal_title | default: "Domestic Journal Papers" }}</h5>
<ul>
{% for pub in member.domestic_journal_items %}
<li data-url="{% if pub.url %}{{ pub.url }}{% endif %}" {% if pub.url %}onclick="window.open(this.dataset.url,'_blank')" style="cursor:pointer"{% endif %}>{{ pub.text | markdownify }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.intl_items %}
<div class="pub-section">
<h5>{{ member.intl_title | default: "International Conference Papers" }}</h5>
<ul>
{% for pub in member.intl_journal_items %}
<li data-url="{% if pub.url %}{{ pub.url }}{% endif %}" {% if pub.url %}onclick="window.open(this.dataset.url,'_blank')" style="cursor:pointer"{% endif %}>{{ pub.text | markdownify }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.domestic_items %}
<div class="pub-section">
<h5>{{ member.domestic_title | default: "Domestic Conference Papers" }}</h5>
<ul>
{% for pub in member.domestic_journal_items %}
<li data-url="{% if pub.url %}{{ pub.url }}{% endif %}" {% if pub.url %}onclick="window.open(this.dataset.url,'_blank')" style="cursor:pointer"{% endif %}>{{ pub.text | markdownify }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

</div>
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
