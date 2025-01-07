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
<p>**End of Principal Investigator**</p> <!-- 디버깅용 -->

<br>

## PhD and Master Students
<div class="row">
{% for member in site.data.team_students %}
  <div class="col-sm-6 clearfix">
    <p>Debug: {{ member.name }}</p> <!-- 디버깅용 -->
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
</div>
<p>**End of PhD and Master Students**</p> <!-- 디버깅용 -->

<br>

## Undergraduate Students
<div class="row">
{% for member in site.data.team_undergraduate_students %}
  <div class="col-sm-6 clearfix">
    <p>Debug: {{ member.name }}</p> <!-- 디버깅용 -->
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
</div>
<p>**End of Undergraduate Students**</p> <!-- 디버깅용 -->

<br>

## Alumni Members
<div class="team-section">
{% for member in site.data.alumni_members %}
  <p>Debug: {{ member.name }}</p> <!-- 디버깅용 -->
  <p><strong>{{ member.name }}</strong>: {{ member.info }}</p>
  <ul>
    {% for i in (1..member.number_educ) %}
      <li>{{ member["education" | append: i] }}</li>
    {% endfor %}
  </ul>
{% endfor %}
</div>
<p>**End of Alumni Members**</p> <!-- 디버깅용 -->
