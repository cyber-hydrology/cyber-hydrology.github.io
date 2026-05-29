---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

{% assign groups = "Principal Investigator:team_professor,POST DOC:team_postdoc,PhD and Master Students:team_students,Undergraduate Students:team_undergraduate_students,Alumni Members:alumni_members" | split: "," %}

{% for group in groups %}
{% assign group_info = group | strip | split: ":" %}
{% assign group_title = group_info[0] %}
{% assign group_data = group_info[1] %}

## {{ group_title }}

<div class="row team-section">

{% for member in site.data[group_data] %}

<div class="col-sm-6 team-member-col">
<div class="team-card">

<div class="team-summary-row">

{% if member.photo %}
<img class="team-thumb" src="{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}

<div class="team-summary-text">
<h3 class="team-name">{{ member.name }}</h3>
</div>

<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>

</div>

<div class="team-detail">

{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}

{% if member.email %}
<p class="team-email">
Email: <a href="mailto:{{ member.email }}">{{ member.email }}</a>
</p>
{% endif %}

{% if member.education1 or member.education2 or member.education3 or member.education4 or member.education5 %}
<h4>Education</h4>
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

{% if member.research_intro %}
<h4>Research Introduction</h4>
<p>{{ member.research_intro }}</p>
{% endif %}

{% if member.research %}
<h4>Research Interests</h4>
<ul>
{% for item in member.research %}
<li>{{ item }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.international_journal_papers %}
<h4>International Journal Papers</h4>
<ul>
{% for paper in member.international_journal_papers %}
<li>{{ paper }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.international_conference_papers %}
<h4>International Conference Papers</h4>
<ul>
{% for paper in member.international_conference_papers %}
<li>{{ paper }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.domestic_journal_papers %}
<h4>Domestic Journal Papers</h4>
<ul>
{% for paper in member.domestic_journal_papers %}
<li>{{ paper }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.domestic_conference_papers %}
<h4>Domestic Conference Papers</h4>
<ul>
{% for paper in member.domestic_conference_papers %}
<li>{{ paper }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.patents %}
<h4>Patents</h4>
<ul>
{% for patent in member.patents %}
<li>{{ patent }}</li>
{% endfor %}
</ul>
{% endif %}

{% if member.awards %}
<h4>Awards</h4>
<ul>
{% for award in member.awards %}
<li>{{ award }}</li>
{% endfor %}
</ul>
{% endif %}

</div>

</div>
</div>

{% endfor %}

</div>

{% endfor %}

<script>
document.addEventListener("DOMContentLoaded", function () {
  var buttons = document.querySelectorAll(".team-toggle-btn");

  buttons.forEach(function (button) {
    button.addEventListener("click", function () {
      var card = button.closest(".team-card");
      var isOpen = card.classList.contains("open");

      card.classList.toggle("open");
      button.textContent = isOpen ? "+" : "−";
    });
  });
});
</script>
