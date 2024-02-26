---
excerpt: "Team members"
permalink: /team/
classes: wide
author_profile: true
---

<style> 
#boxcolor {
  background-color: #1F416F ;
  border-radius: 5%;
  padding: 50px;
} 
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
  color: white;
}
.centeralign2 {
  text-align: center;
  color: #1F416F;
}
</style>

<h1 class="centeralign2"> <b>Team </b></h1>

<div class="container">
<div id="boxcolor">
<div class="row">
  {% for member in site.data.team_members %}
  <div class="col-md-4" style="height:300px;">
    <a href="{{ site.url }}{{ site.baseurl }}/team/{{member.url}}">
    <div class="mask">
      <img src="{{ site.url }}{{ site.baseurl }}/assets/images/teampic/{{ member.photo}}" width="25%" class="image teamImage">
    </div>
    </a>
      <p class="centeralign"> <b>{{member.name }}</b>
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