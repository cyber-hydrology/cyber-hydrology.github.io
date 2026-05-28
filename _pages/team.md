---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

## Principal Investigator

<div class="team-grid">
{% for member in site.data.team_professor %}
<div class="team-card">
{% if member.photo %}
<img class="team-photo" src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}
<div class="team-basic">
<div class="team-name-row">
<h3>{{ member.name }}</h3>
<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>
</div>
{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
{% if member.education1 %}
<p class="team-education">{{ member.education1 }}</p>
{% endif %}
</div>
<div class="team-detail">
{% include team_member_detail.html member=member %}
</div>
</div>
{% endfor %}
</div>

## POST DOC

<div class="team-grid">
{% for member in site.data.team_postdoc %}
<div class="team-card">
{% if member.photo %}
<img class="team-photo" src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}
<div class="team-basic">
<div class="team-name-row">
<h3>{{ member.name }}</h3>
<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>
</div>
{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
{% if member.education1 %}
<p class="team-education">{{ member.education1 }}</p>
{% endif %}
</div>
<div class="team-detail">
{% include team_member_detail.html member=member %}
</div>
</div>
{% endfor %}
</div>

## PhD and Master Students

<div class="team-grid">
{% for member in site.data.team_students %}
<div class="team-card">
{% if member.photo %}
<img class="team-photo" src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}
<div class="team-basic">
<div class="team-name-row">
<h3>{{ member.name }}</h3>
<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>
</div>
{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
{% if member.education1 %}
<p class="team-education">{{ member.education1 }}</p>
{% endif %}
{% if member.research %}
<ul class="team-research-short">
{% for item in member.research limit:2 %}
<li>{{ item }}</li>
{% endfor %}
</ul>
{% endif %}
</div>
<div class="team-detail">
{% include team_member_detail.html member=member %}
</div>
</div>
{% endfor %}
</div>

## Undergraduate Students

<div class="team-grid">
{% for member in site.data.team_undergraduate_students %}
<div class="team-card">
{% if member.photo %}
<img class="team-photo" src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}
<div class="team-basic">
<div class="team-name-row">
<h3>{{ member.name }}</h3>
<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>
</div>
{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
{% if member.education1 %}
<p class="team-education">{{ member.education1 }}</p>
{% endif %}
{% if member.research %}
<ul class="team-research-short">
{% for item in member.research limit:2 %}
<li>{{ item }}</li>
{% endfor %}
</ul>
{% endif %}
</div>
<div class="team-detail">
{% include team_member_detail.html member=member %}
</div>
</div>
{% endfor %}
</div>

## Alumni Members

<div class="team-grid">
{% for member in site.data.alumni_members %}
<div class="team-card">
{% if member.photo %}
<img class="team-photo" src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}">
{% endif %}
<div class="team-basic">
<div class="team-name-row">
<h3>{{ member.name }}</h3>
<button class="team-toggle-btn" type="button" aria-label="show detail">+</button>
</div>
{% if member.info %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
{% if member.education1 %}
<p class="team-education">{{ member.education1 }}</p>
{% endif %}
</div>
<div class="team-detail">
{% include team_member_detail.html member=member %}
</div>
</div>
{% endfor %}
</div>

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
