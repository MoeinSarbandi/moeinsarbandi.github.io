---
layout: page
title: projects
permalink: /projects/
description: Supervised MSc projects in control systems and wind energy.
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

## Future student projects

<div class="future-projects-placeholder">
  <span class="future-projects-label">Future opportunities</span>
  <p>To be announced soon.</p>
</div>

<style>
  .future-projects-placeholder {
    margin: 1rem 0 2rem;
    padding: 1.5rem;
    border: 1px dashed var(--global-divider-color, #d7d7d7);
    border-radius: 0.75rem;
    text-align: center;
  }

  .future-projects-label {
    color: var(--global-theme-color, #b509ac);
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.09em;
    text-transform: uppercase;
  }

  .future-projects-placeholder p {
    margin: 0.35rem 0 0;
    color: var(--global-text-color, #111);
    font-size: 1.15rem;
    font-weight: 600;
  }
</style>
