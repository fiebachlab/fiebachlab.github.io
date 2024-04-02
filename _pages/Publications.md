---
excerpt: "Publications"
permalink: publications/
classes: wide
years: [2024,2023,2022,2021,2020,2019,2018,2017,2016, 2015, 2013, 2012,2011,2010,2009,2008,2007,2005,2004,2003,2002]
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


<h6 class="centeralign2"> Submitted / in preparation </h6>
<ol type="1" class="text-justify"> <small>
<li>Basten, U., Rammensee, R. A., Weygandt, R., & Fiebach, C. J. (in preparation). Intelligence and the regulation of the brain’s default activity. </li>
<li>Wehrheim, M., Faskowitz, J., García Alanis, J. C., Schubert, A.-L., & Fiebach, C. J. (preprint). Reliability of Variability and Complexity Measures for Task and Task-Free BOLD fMRI. Preprint DOI: https://osf.io/preprints/psyarxiv/ves2t </li>
</small>
</ol>   


{% for y in page.years %}
  
  {% bibliography -f references -q @*[year={{y}}]* %}
{% endfor %}
[//]:<h6 id="{{y}}" class="centeralign2">{{y}}</h6>