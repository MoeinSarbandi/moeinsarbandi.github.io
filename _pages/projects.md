---
layout: page
title: projects
permalink: /projects/
description: Current and completed MSc projects in control systems and wind energy.
nav: true
nav_order: 3
horizontal: false
---

I supervise student projects at the intersection of nonlinear control, data-driven methods, learning-based control, and floating offshore wind turbines. The topics below combine a clear research question with reproducible simulation or data analysis.

## Current student projects

The following topics are assigned to EU-CORE MSc students. Each project starts with a focused, achievable core study and includes optional research extensions for students who make strong progress.

<div class="student-opportunities">
  {% assign student_projects = site.projects | where: "category", "opportunity" | sort: "importance" %}
  {% for project in student_projects %}
    <article class="student-opportunity">
      <div class="student-opportunity-meta">
        <span>{{ project.project_id }}</span>
        <span>{{ project.status | default: "EU-CORE MSc" }} · EU-CORE MSc</span>
      </div>
      {% if project.image %}
        <a class="student-opportunity-image-link" href="{{ project.url | relative_url }}" aria-label="View {{ project.title | escape }}">
          <img class="student-opportunity-image" src="{{ project.image | relative_url }}" alt="{{ project.title | escape }}" loading="lazy">
        </a>
      {% endif %}
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p>{{ project.description }}</p>
      {% if project.students %}
        <p class="student-opportunity-students"><strong>Students:</strong> {{ project.students | join: " &amp; " }}</p>
      {% endif %}
      {% if project.topics %}
        <div class="student-opportunity-topics" aria-label="Project topics">
          {% for topic in project.topics %}<span>{{ topic }}</span>{% endfor %}
        </div>
      {% endif %}
      <a class="student-opportunity-link" href="{{ project.url | relative_url }}">
        View project details <i class="fa-solid fa-arrow-right" aria-hidden="true"></i>
      </a>
    </article>
  {% endfor %}
</div>

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

<style>
  .student-opportunities {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
    margin: 1.25rem 0 2rem;
  }

  .student-opportunity {
    display: flex;
    flex-direction: column;
    padding: 1.35rem;
    border: 1px solid var(--global-divider-color, #d7d7d7);
    border-radius: 0.85rem;
    background: var(--global-bg-color, #fff);
    box-shadow: 0 0.45rem 1.3rem rgba(0, 0, 0, 0.045);
  }

  .student-opportunity-meta {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 0.4rem 0.8rem;
    margin-bottom: 0.65rem;
    color: var(--global-theme-color, #b509ac);
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.09em;
    text-transform: uppercase;
  }

  .student-opportunity-image-link {
    display: block;
    margin-bottom: 0.9rem;
  }

  .student-opportunity-image {
    display: block;
    width: 100%;
    height: auto;
    aspect-ratio: 4 / 3;
    object-fit: contain;
    border-radius: 0.5rem;
  }

  .student-opportunity h3 {
    margin: 0 0 0.65rem;
    font-size: 1.15rem;
    font-weight: 600;
    line-height: 1.35;
  }

  .student-opportunity p {
    margin-bottom: 0.9rem;
    color: var(--global-text-color-light, #555);
    font-size: 0.9rem;
    line-height: 1.55;
  }

  .student-opportunity-topics {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    margin: auto 0 1rem;
  }

  .student-opportunity-topics span {
    padding: 0.22rem 0.52rem;
    border-radius: 999px;
    background: color-mix(in srgb, var(--global-theme-color, #b509ac) 9%, var(--global-bg-color, #fff));
    color: var(--global-text-color-light, #555);
    font-size: 0.72rem;
  }

  .student-opportunity-link {
    font-size: 0.84rem;
    font-weight: 600;
  }

  .student-opportunity-link i {
    margin-left: 0.25rem;
    font-size: 0.72rem;
    transition: transform 150ms ease;
  }

  .student-opportunity-link:hover i {
    transform: translateX(0.18rem);
  }

  @media (max-width: 760px) {
    .student-opportunities {
      grid-template-columns: 1fr;
    }
  }
</style>
