---
excerpt: "About Wehrheim"
permalink: /team/wehrheim
classes: wide
---

<style> 
.teamImage{
    width: 300px;
    height: 300px;
    object-fit: cover;
    border-radius: 50%;
    display: block;
    margin-left: auto;
    margin-right: auto;
} 

.centeralign {
  text-align: center;
}
#boxcolor {
  background-color: #1F416F ;
  padding: 50px;
    border-radius: 20px;
} 
.white {
  color: white;
}
.centeralign2 {
  font-weight: bold;
  color: white;
}
</style>



{% for member in site.data.team_members %}
{% if member.name == "Maren Wehrheim, M.Sc." %}
<div id="boxcolor">
<div class="row">
    <div class="col-md-6">
        <h3 class="centeralign2">{{member.name }}</h3> 
        <p class="white"><b>{{member.title}}</b> <br>
        {{member.fon}}<br>
        {{member.office}}<br>
        {{member.mail}}
        </p>
    </div>
    <div class="col-md-6">
        <div class="mask">
        <img src="{{ site.url }}/assets/images/teampic/{{ member.photo }}" width="25%" class="image teamImage">
        </div>
    </div>
</div>
</div>
<br>
<div>
    <b> Research Interests:</b>
    <br>
    {{member.research_interests}}
</div>

{% endif %}
{% endfor %}