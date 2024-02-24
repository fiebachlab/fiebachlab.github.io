---
title: "Team"
excerpt: "Team members"
permalink: /team/
classes: wide
author_profile: true
---

<style> 
.teamImage{
    width: 150px;
    height: 150px;
    object-fit: cover;
    border-radius: 50%;
    display: block;
    margin-left: auto;
    margin-right: auto;
} 

.centeralign {
  text-align: center;
}

</style>

<br>
<div class="container">
<div class="row">
  {% for member in site.data.team_members %}
  <div class="col-md-4" style="height:300px;">
    <a href="{{ site.url }}{{ site.baseurl }}/team/fiebach">
    <div class="mask">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" width="25%" class="image teamImage">
    </div>
    </a>
      <p class="centeralign"> <b>{{member.name }}</b> 
      <br>
      {{member.title}} </p>
  </div>
  {% endfor %}
</div>
</div>


<style> 
.row::after {
  content: "";
  clear: both;
  display: table;
}
</style>