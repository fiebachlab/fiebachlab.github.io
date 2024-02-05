---
title: "Team"
excerpt: "Team members"
permalink: /team/
---
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}
<div class="col-sm-6 clearfix">
<div style="text-align:center">
  <h4><b>{{member.name }}</b></h4>
  <a href="{{member.url}}">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive center-block" width="25%">
    </a>
  <br>

  <h4>{{member.title}}</h4>
  {{ member.affiliation }}
  </div>
  {{ member.about }}
  
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
