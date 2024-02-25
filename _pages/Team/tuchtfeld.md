---
excerpt: "About Tuchtfeld"
permalink: /team/tuchtfeld
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

</style>



{% for member in site.data.team_members %}
{% if member.name == "Sabine Tuchtfeld" %}
<div class="row">
    <div class="col-md-6">
        <p> <h1>{{member.name }}</h1> 
        <b>{{member.title}}</b> <br>
        {{member.fon}}<br>
        {{member.secretary}}<br>
        {{member.office}}<br>
        {{member.office}}</p><br>
    </div>
    <div class="col-md-6">
        <div class="mask">
        <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" width="25%" class="image teamImage">
        </div>
    </div>
</div>

<div>
    <b> Research Interests:</b>
    <br>
    {{member.research_interests}}
</div>

{% endif %}
{% endfor %}