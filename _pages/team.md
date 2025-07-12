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

{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

  {%- if forloop.first -%}  {#––– PRINCIPAL PROFILE –––#}
<div class="row">
  <div class="col-sm-12 clearfix text-center">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="180px" style="margin:0 auto;border-radius:50%;">
    <h3><a href="mailto:{{ member.email }}">{{ member.name }}</a></h3>
    <i>{{ member.info }}</i>
    <ul style="list-style:none;padding:0;margin-top:15px;">
      {% if member.number_educ >= 1 %}<li>{{ member.education1 }}</li>{% endif %}
      {% if member.number_educ >= 2 %}<li>{{ member.education2 }}</li>{% endif %}
      {% if member.number_educ >= 3 %}<li>{{ member.education3 }}</li>{% endif %}
      {% if member.number_educ >= 4 %}<li>{{ member.education4 }}</li>{% endif %}
      {% if member.number_educ == 5 %}<li>{{ member.education5 }}</li>{% endif %}
    </ul>
  </div>
</div>
  {%- else -%}            {#––– SECONDARY PROFILES –––#}

    {% assign even_odd = number_printed | modulo: 2 %}
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

    {% assign number_printed = number_printed | plus: 1 %}
    {% if even_odd == 1 %}
</div>
    {% endif %}

  {%- endif -%}

{% endfor %}

{% if number_printed | modulo: 2 == 1 %}
</div>
{% endif %}
