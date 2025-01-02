---
excerpt: ""
permalink: publications/
layout: splash
author_profile: false
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/Frankfurt_Skyline_at_Night.jpg
title: "Publications"
years: [2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002]
---


<h6 class="centeralign2">Published</h6>
{% for y in page.years %}
  {% bibliography -f references -q @*[year={{y}}]* %}
{% endfor %}

  