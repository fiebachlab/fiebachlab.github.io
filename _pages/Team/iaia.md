---
excerpt: "About Iaia"
permalink: /team/iaia
classes: wide
---


{% for member in site.data.team_members %}
{% if member.name == "Dr. Cosimo Iaia" %}
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
        <img src="../assets/images/teampic/{{ member.photo }}" width="25%" class="image teamImage">
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