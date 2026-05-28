---
title: "Noh Lab - Team"
layout: gridlay
excerpt: "Noh Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

{% assign groups = 
  "Principal Investigator:team_professor,
   POST DOC:team_postdoc,
   PhD and Master Students:team_students,
   Undergraduate Students:team_undergraduate_students,
   Alumni Members:alumni_members" | split: "," 
%}

{% for group in groups %}
  {% assign group_info = group | strip | split: ":" %}
  {% assign group_title = group_info[0] %}
  {% assign group_data = group_info[1] %}

## {{ group_title }}

<div class="team-grid">

{% for member in site.data[group_data] %}

<div class="team-card">

  <div class="team-card-top">
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
  </div>

  <div class="team-detail">

    {% if member.email %}
    <p class="team-email">
      Email: <a href="mailto:{{ member.email }}">{{ member.email }}</a>
    </p>
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

{% endfor %}

</div>

{% endfor %}

<script>
document.addEventListener("DOMContentLoaded", function () {
  const buttons = document.querySelectorAll(".team-toggle-btn");

  buttons.forEach(function (button) {
    button.addEventListener("click", function () {
      const card = button.closest(".team-card");
      const isOpen = card.classList.contains("open");

      card.classList.toggle("open");
      button.textContent = isOpen ? "+" : "−";
    });
  });
});
</script>
