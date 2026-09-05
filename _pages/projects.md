---
layout: page
title: projects
permalink: /projects/
description: Supervised MSc projects and open research topics in control systems and wind energy.
nav: true
nav_order: 3
horizontal: false
---

I supervise student projects at the intersection of nonlinear control, data-driven methods, learning-based control, and floating offshore wind turbines. The topics below combine a clear research question with reproducible simulation or data analysis.

## Completed supervised projects

These projects were completed by MSc students in the EU-CORE European Master Programme at École Centrale Nantes.

<div class="projects">
  {% assign supervised_projects = site.projects | where: "category", "supervision" | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-2">
    {% for project in supervised_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>

## Open topics for students

The following topics are suitable for an MSc project, research internship, or exploratory collaboration. The exact scope can be adapted to the student's background and the available project period.

<div class="projects">
  {% assign open_projects = site.projects | where: "category", "open" | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in open_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>

Interested students are welcome to [contact me](mailto:moein.sarbandi@ec-nantes.fr) with a short CV, their relevant coursework, and the topic that interests them most.
