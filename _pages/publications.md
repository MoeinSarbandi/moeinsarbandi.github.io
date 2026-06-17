---
layout: page
permalink: /publications/
title: publications
description: 
nav: true
nav_order: 2
---

{% include bib_search.liquid %}

## Journal Articles

<div class="publications">
{% bibliography --query @article %}
</div>

## Conference Papers

<div class="publications">
{% bibliography --query @inproceedings %}
</div>
