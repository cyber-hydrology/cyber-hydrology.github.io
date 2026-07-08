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

<h3 class="member-toggle-name">{{ member.name }} <span class="toggle-arrow">▼</span></h3>

<div class="member-detail-panel professor-detail-panel">

{% if member.info %}
<p>{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p>Email: {{ member.email }}</p>
{% endif %}

{% if member.education1 or member.education2 or member.education3 or member.education4 or member.education5 %}
<ul class="professor-list">
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

{% assign has_pubs = false %}
{% if member.intl_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_journal_items %}{% assign has_pubs = true %}{% endif %}
{% if member.intl_items %}{% assign has_pubs = true %}{% endif %}
{% if member.domestic_items %}{% assign has_pubs = true %}{% endif %}

<div class="memberbox">

{% if member.photo %}
<div class="member-photo-box">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="member-photo" alt="{{ member.name }}">
</div>
{% endif %}

<div class="member-info-box">

{% if has_pubs %}
<h3 class="member-toggle-name">{{ member.name }} <span class="toggle-arrow">▼</span></h3>
{% else %}
<h3>{{ member.name }}</h3>
{% endif %}

{% if member.info %}
<p>{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p>Email:<br>{{ member.email }}</p>
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

</div>

</div>

{% if has_pubs %}
<div class="member-detail-panel">

{% if member.intl_journal_items %}
<div class="pub-section">
<h5>{{ member.intl_journal_title | default: "International Journal Papers" }}</h5>
<ul>
{% for pub in member.intl_journal_items %}
<li>{{ pub.text | markdownify | remove: '<p>' | remove: '</p>' }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.domestic_journal_items %}
<div class="pub-section">
<h5>{{ member.domestic_journal_title | default: "Domestic Journal Papers" }}</h5>
<ul>
{% for pub in member.domestic_journal_items %}
<li>{{ pub.text | markdownify | remove: '<p>' | remove: '</p>' }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.intl_items %}
<div class="pub-section">
<h5>{{ member.intl_title | default: "International Conference Papers" }}</h5>
<ul>
{% for pub in member.intl_items %}
<li>{{ pub.text | markdownify | remove: '<p>' | remove: '</p>' }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if member.domestic_items %}
<div class="pub-section">
<h5>{{ member.domestic_title | default: "Domestic Conference Papers" }}</h5>
<ul>
{% for pub in member.domestic_items %}
<li>{{ pub.text | markdownify | remove: '<p>' | remove: '</p>' }}</li>
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

{% endif %}

{% endfor %}

</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  var toggleNames = document.querySelectorAll(".member-toggle-name");

  toggleNames.forEach(function (toggleName) {
    toggleName.addEventListener("click", function () {
      var parentBox = toggleName.closest(".col-sm-6, .professor-card");
      if (!parentBox) return;

      var detailPanel = parentBox.querySelector(".member-detail-panel");
      if (!detailPanel) return;

      toggleName.classList.toggle("open");
      detailPanel.classList.toggle("open");
    });
  });
});
</script>
