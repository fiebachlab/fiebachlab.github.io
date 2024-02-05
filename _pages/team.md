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
  <div class="column">
    <a href="{{member.url}}">
    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive center-block" width="25%">
    </a>
  <br>
  </div>
  <div class="column">
      <h4><b>{{member.name }}</b></h4>
      <h4>{{member.title}}</h4>
      {{ member.affiliation }}
      {{ member.about }}
  </div>
  <div class="column">
   
    {{ member.fon }}
    {{ member.secretary }}
    {{ member.office }}
    {{ member.mail }}
  </div>
</div> 


<style type="text/css">
  p {
    .column {
    float: left;
    width: 33.33%;
  }
  /* Clear floats after the columns */
  .row:after {
    content: "";
    display: table;
    clear: both;

  }

  }
</style>


{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}
