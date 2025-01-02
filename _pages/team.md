---
excerpt: "Team members"
permalink: /team/
classes: wide
author_profile: true
---

<h1 class="centeralign2"> <b>Team </b></h1>

<div class="container">
<div id="boxcolor">
<div class="row">
  {% for member in site.data.team_members %}
  <div class="col-md-4" style="height:300px;">
    <a href="{{member.url}}">
    <div class="mask">
      <img src="../assets/images/teampic/{{ member.photo}}" width="25%" class="image teamImageSmall">
    </div>
    </a>
      <p class="centeralign" style="color:white;"> <b>{{member.name }}</b>
      <br> {{member.title}} </p>
  </div>
  {% endfor %}
</div>
</div>
</div>

<style> 
.row::after {
  content: "";
  clear: both;
  display: table;
}
</style>