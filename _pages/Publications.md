---
excerpt: "Publications"
permalink: publications/
classes: wide
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
    {% bibliography -f references --order descending %}
{% endfor %}
