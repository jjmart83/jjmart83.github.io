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

<!-- Principal member: Juan J. Martínez -->
<div class="row">
  <div class="col-sm-12 clearfix text-center">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/JJM_2.jpg" class="img-responsive" width="180px" style="margin: 0 auto; border-radius: 50%;" />
    <h3><a href="mailto:bio.jjmartinez@gmail.com">Juan J. Martínez</a></h3>
    <i>
      I grew up in a small town in Jujuy and studied in Córdoba, Argentina, before moving to Canada in 2012 to join McGill University as a post-doctoral fellow. I earned both my Bachelor of Science in Biological Sciences and my Doctoral degree in Biology from the National University of Córdoba, and later divided my time between Córdoba and Río Cuarto during my post-doctoral work. I was fortunate during my PhD to be supervised by Dr. Noemí Gardenal, and later to work with Dr. José Priotto and Dr. Virginie Millien during my post-doc. Inspired by them, I have focused my research broadly on population genetics, with a particular interest in phenotypic evolution — how populations diverge and which evolutionary forces, such as selection or genetic drift, shape this differentiation. To address these questions, I combine my background in population genetics and evolutionary ecology to explore how natural populations respond to environmental change.
    </i>
    <ul style="list-style: none; padding: 0; margin-top: 15px;">
      <li>Biólogo, Universidad Nacional de Córdoba</li>
      <li>Doctor en Ciencias Biológicas, Universidad Nacional de Córdoba</li>
      <li>Postdoc CONICET, Universidad Nacional de Río Cuarto</li>
      <li>Postdoc, McGill University</li>
      <li>Investigador Independiente de CONICET</li>
    </ul>
    <p style="margin-top: 10px;">
      <a href="https://orcid.org/0000-0000-0000-0000" target="_blank">ORCID</a> |
      <a href="https://twitter.com/tu_usuario" target="_blank">Twitter</a> |
      <a href="https://scholar.google.com/citations?user=XXXXX" target="_blank">Google Scholar</a>
    </p>
  </div>
</div>

<!-- Other team members -->
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  {% unless member.name == "Juan J. Martínez" %}

  {% assign even_odd = number_printed | modulo: 2 %}
  {% if even_odd == 0 %}
  <div class="row">
  {% endif %}

  <div class="col-sm-6 clearfix">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="40%" style="float: left; margin-right: 15px;" />
    <h4>{{ member.name }}</h4>
    <i>{{ member.info }}</i>
    <ul style="overflow: hidden">
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

  {% endunless %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}
