---
excerpt: "Publications"
permalink: publications/
classes: wide
years: [
  2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 
  2016, 2015, 2013, 2012, 2011, 2010, 2009, 2008, 
  2007, 2005, 2004, 2003, 2002
]
---

<style>
.centeralign {
  text-align: center;
  color:#1F416F;
  font-weight: bold;
}
.centeralign2 {
  color:#1F416F;
  font-weight: bold;
}
</style>

<h6 class="centeralign2">Pre-Prints</h6>
{% bibliography -f preprints %}


<h6 class="centeralign2">In Preparation</h6>
<ol type="1" class="text-justify"> 
<li>Miederer, I., Buchholz, H.-G., Rademacher, L., Eckart, C., Kraft, D., Piel, M., Fiebach, C. J., & Mathias Schreckenberger, M. (in preparation). Dopaminergic mechanisms of cognitive flexibility: an [18F]fallypride PET study. </li>

<li>Basten, U., Rammensee, R. A., Weygandt, R., & Fiebach, C. J. (in preparation). Intelligence and the regulation of the brain’s default activity.</li>

<li>Krasberg-Schoett, M. J. S., Deichmann, R., Fischmann, T., Fiebach, C. J. (in preparation). Rejecting the rejected child – neural correlates of social exclusion depend on child attachment.</li>

<li> Armbruster-Genç, D. J. N, Basten, U., & Fiebach, C. J. (in preparation). Reliability for an Experimental Assessment of Cognitive Flexibility and Stability.</li>

</ol>   

<h6 class="centeralign2">Published</h6>
{% for y in page.years %}
  {% if y %}
    {% bibliography -f references -q @*[year={{y}}]* %}
  {% endif %}
{% endfor %}
