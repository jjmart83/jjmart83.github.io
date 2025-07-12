---
title: "JJ Martinez - Colaboradores"
layout: gridlay
excerpt: "People"
sitemap: false
permalink: /team/
---

# People

 **Do you want to join us?** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**


## LEEB (Lab de Ecología Evolutiva y Biogeografía) members

{%- comment -%}
/* -------- 1. Principal profile -------- */
{%- endcomment -%}
{% assign leader = site.data.team_members | where: "name", "Juan J. Martínez" | first %}
{% if leader %}
<div class="row">
  <div class="col-sm-12 text-center">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ leader.photo }}" class="img-responsive" width="180" style="margin:0 auto;border-radius:50%;">
    <h3><a href="mailto:{{ leader.email }}">{{ leader.name }}</a></h3>
    <i>{{ leader.info }}</i>
    <ul style="list-style:none;padding:0;margin-top:15px;">
      {% if leader.number_educ >= 1 %}<li>{{ leader.education1 }}</li>{% endif %}
      {% if leader.number_educ >= 2 %}<li>{{ leader.education2 }}</li>{% endif %}
      {% if leader.number_educ >= 3 %}<li>{{ leader.education3 }}</li>{% endif %}
      {% if leader.number_educ >= 4 %}<li>{{ leader.education4 }}</li>{% endif %}
      {% if leader.number_educ == 5 %}<li>{{ leader.education5 }}</li>{% endif %}
    </ul>
  </div>
</div>
{% endif %}

{%- comment -%}
/* -------- 2. Everyone else in two columns -------- */
{%- endcomment -%}
{% assign others = site.data.team_members | reject: "name", "Juan J. Martínez" %}
{% assign printed = 0 %}
{% for member in others %}
  {% assign even_odd = printed | modulo: 2 %}
  {% if even_odd == 0 %}
<div class="row">
  {% endif %}

  <div class="col-sm-6 clearfix">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="40%" style="float:left;margin-right:15px;">
    <h4>{{ member.name }}</h4>
    <i>{{ member.info }}</i>
    <ul style="overflow:hidden;">
      {% if member.number_educ >= 1 %}<li>{{ member.education1 }}</li>{% endif %}
      {% if member.number_educ >= 2 %}<li>{{ member.education2 }}</li>{% endif %}
      {% if member.number_educ >= 3 %}<li>{{ member.education3 }}</li>{% endif %}
      {% if member.number_educ >= 4 %}<li>{{ member.education4 }}</li>{% endif %}
      {% if member.number_educ == 5 %}<li>{{ member.education5 }}</li>{% endif %}
    </ul>
  </div>

  {% assign printed = printed | plus: 1 %}
  {% if even_odd == 1 %}
</div>
  {% endif %}
{% endfor %}
{% if printed | modulo: 2 == 1 %}
</div>
{% endif %}
