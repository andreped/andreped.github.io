---
layout: page
permalink: /research/
title: research
description: selection of publications I have contributed to, either peer-reviewed or preprints.
years: [2021, 2019]
nav: true
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
