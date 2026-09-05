---
layout: page
permalink: /activities/
title: academic activities
description: Peer-review service, invited talks, and conference presentations.
nav: true
nav_order: 5
---

Peer-review service, invited talks, and conference presentations are collected here in a compact record. Select a section to view its details.

<div class="activity-sections">
  <details class="activity-section" name="academic-activities">
    <summary>
      <span class="activity-heading">
        <span class="activity-kicker">Service</span>
        <span class="activity-title">Peer-review service</span>
        <span class="activity-summary">30+ journal reviews across six journals, plus conference and community service</span>
      </span>
      <span class="activity-chevron" aria-hidden="true"><i class="fa-solid fa-chevron-down"></i></span>
    </summary>

    <div class="activity-content">
      <p class="activity-note">
        I review work in automatic control, nonlinear systems, and wind-energy applications. Manuscript-level details are not disclosed to preserve reviewer confidentiality.
      </p>

      <div class="activity-columns">
        <section>
          <h2>Journal reviewing</h2>
          <ul class="activity-list">
            <li><span>Automatica</span></li>
            <li><span>IEEE Transactions on Cybernetics</span></li>
            <li><span>ISA Transactions</span></li>
            <li><span>Wind Engineering</span></li>
            <li><span>Energy Reports</span></li>
            <li><span>Scientific Reports</span></li>
          </ul>
        </section>

        <section>
          <h2>Conference and community service</h2>
          <ul class="activity-list activity-list-detailed">
            <li>
              <span>23rd IFAC World Congress</span>
              <small>Reviewer · 2026</small>
            </li>
            <li>
              <span>American Control Conference</span>
              <small>Reviewer · 2026</small>
            </li>
            <li>
              <span>Wind Energy Science Conference</span>
              <small>Organizing committee · Nantes · 2025</small>
            </li>
          </ul>
        </section>
      </div>
    </div>

  </details>

  <details class="activity-section" name="academic-activities">
    <summary>
      <span class="activity-heading">
        <span class="activity-kicker">Knowledge exchange</span>
        <span class="activity-title">Invited &amp; technical talks</span>
        <span class="activity-summary">Lectures, workshops, and tutorials for academic audiences</span>
      </span>
      <span class="activity-chevron" aria-hidden="true"><i class="fa-solid fa-chevron-down"></i></span>
    </summary>

    <div class="activity-content activity-records">
      <article class="activity-record">
        <p class="activity-meta">February 2026 · École Centrale Nantes, France</p>
        <h2>Data-Based Control Application to Wind Turbines</h2>
        <p><a href="https://www.ec-nantes.fr/centrale-nantes/news/eu-core-winter-school-2026">EU-CORE Winter School 2026</a></p>
      </article>

      <article class="activity-record">
        <p class="activity-meta">February 2026 · École Centrale Méditerranée, Marseille, France</p>
        <h2>Novel Wind Speed Estimation Method for Wind Turbines Using the Sliding-Mode Approach</h2>
        <p><a href="https://www.jse-2026.fr/">Journées Scientifiques de l'Éolien 2026</a></p>
      </article>

      <article class="activity-record">
        <p class="activity-meta">October 2025 · ENSEEIHT, Toulouse, France</p>
        <h2>Data-Based Sliding-Mode Control — Application to Floating Offshore Wind Turbines</h2>
        <p><a href="https://pkergus.github.io/workshop_datadriven.html">GDR MACS Workshop on Data-Driven Control and Analysis of Dynamical Systems</a></p>
      </article>

      <article class="activity-record">
        <p class="activity-meta">2025 · École Centrale Nantes, France</p>
        <h2>Tutorial: Introduction to OpenFAST with MATLAB/Simulink</h2>
        <p>Orientation session for incoming EU-CORE students</p>
      </article>
    </div>

  </details>

  <details class="activity-section" name="academic-activities">
    <summary>
      <span class="activity-heading">
        <span class="activity-kicker">Research dissemination</span>
        <span class="activity-title">Conference presentations</span>
        <span class="activity-summary">Presented and upcoming contributions at international control and wind-energy events</span>
      </span>
      <span class="activity-chevron" aria-hidden="true"><i class="fa-solid fa-chevron-down"></i></span>
    </summary>

    <div class="activity-content activity-records">
      <article class="activity-record">
        <p class="activity-meta">August 2026 · Busan, Republic of Korea</p>
        <h2>Robust Control Based on a New Wind Speed Observer for Floating Wind Turbines</h2>
        <p>23rd IFAC World Congress</p>
      </article>

      <article class="activity-record">
        <p class="activity-meta">May 2026 · Bruges, Belgium</p>
        <h2>Control of Floating Offshore Wind Turbines via Control Lyapunov Function-Based Quadratic Programming and Adaptive Super-Twisting</h2>
        <p>TORQUE 2026 · <a href="https://doi.org/10.1088/1742-6596/3224/5/052032">View paper</a></p>
      </article>

      <article class="activity-record">
        <p class="activity-meta">2025 · Nantes, France</p>
        <h2>Robust Adaptive Super-Twisting Control for Floating Wind Turbines in Region III</h2>
        <p>Wind Energy Science Conference</p>
      </article>

      <article class="activity-record activity-record-upcoming">
        <p class="activity-meta"><span class="activity-badge">Upcoming</span> September 2026 · École Centrale Nantes</p>
        <h2>Data-Based Sliding-Mode Control: From Estimation to Data-Driven Design</h2>
        <p>CODEx internal seminar</p>
      </article>
    </div>

  </details>
</div>

<style>
  .activity-sections {
    display: grid;
    gap: 1rem;
    margin-top: 2rem;
  }

  .activity-section {
    overflow: hidden;
    border: 1px solid var(--global-divider-color, #d7d7d7);
    border-radius: 0.75rem;
    background: var(--global-bg-color, #fff);
    transition:
      border-color 160ms ease,
      box-shadow 160ms ease;
  }

  .activity-section[open] {
    border-color: color-mix(in srgb, var(--global-theme-color, #b509ac) 55%, var(--global-divider-color, #d7d7d7));
    box-shadow: 0 0.65rem 1.6rem rgba(0, 0, 0, 0.08);
  }

  .activity-section summary {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1.5rem;
    padding: 1.25rem 1.4rem;
    cursor: pointer;
    list-style: none;
  }

  .activity-section summary::-webkit-details-marker {
    display: none;
  }

  .activity-section summary:focus-visible {
    outline: 3px solid color-mix(in srgb, var(--global-theme-color, #b509ac) 35%, transparent);
    outline-offset: -3px;
  }

  .activity-heading {
    display: grid;
    min-width: 0;
  }

  .activity-kicker {
    margin-bottom: 0.15rem;
    color: var(--global-theme-color, #b509ac);
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.09em;
    text-transform: uppercase;
  }

  .activity-title {
    color: var(--global-text-color, #111);
    font-size: clamp(1.15rem, 2.5vw, 1.4rem);
    font-weight: 600;
    line-height: 1.3;
  }

  .activity-summary {
    margin-top: 0.25rem;
    color: var(--global-text-color-light, #666);
    font-size: 0.9rem;
    line-height: 1.45;
  }

  .activity-chevron {
    flex: 0 0 auto;
    color: var(--global-theme-color, #b509ac);
    transition: transform 160ms ease;
  }

  .activity-section[open] .activity-chevron {
    transform: rotate(180deg);
  }

  .activity-content {
    padding: 0 1.4rem 1.4rem;
    border-top: 1px solid var(--global-divider-color, #d7d7d7);
  }

  .activity-note {
    margin: 1.2rem 0;
    color: var(--global-text-color-light, #666);
    font-size: 0.94rem;
  }

  .activity-columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 2rem;
  }

  .activity-columns h2,
  .activity-record h2 {
    margin: 0;
    color: var(--global-text-color, #111);
    font-size: 1rem;
    font-weight: 600;
    line-height: 1.45;
  }

  .activity-columns h2 {
    margin-bottom: 0.6rem;
  }

  .activity-list {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .activity-list li {
    padding: 0.5rem 0;
    border-top: 1px solid var(--global-divider-color, #d7d7d7);
  }

  .activity-list li:first-child {
    border-top: 0;
  }

  .activity-list-detailed li {
    display: grid;
    gap: 0.1rem;
  }

  .activity-list small,
  .activity-meta {
    color: var(--global-text-color-light, #666);
    font-size: 0.82rem;
  }

  .activity-records {
    padding-top: 0.1rem;
  }

  .activity-record {
    padding: 1.1rem 0;
    border-top: 1px solid var(--global-divider-color, #d7d7d7);
  }

  .activity-record:first-child {
    border-top: 0;
  }

  .activity-record p {
    margin: 0.35rem 0 0;
    line-height: 1.5;
  }

  .activity-record .activity-meta {
    margin: 0 0 0.25rem;
  }

  .activity-record-upcoming {
    border-left: 3px solid var(--global-theme-color, #b509ac);
    padding-left: 1rem;
  }

  .activity-badge {
    display: inline-block;
    margin-right: 0.45rem;
    padding: 0.16rem 0.48rem;
    border-radius: 999px;
    background: color-mix(in srgb, var(--global-theme-color, #b509ac) 12%, transparent);
    color: var(--global-theme-color, #b509ac);
    font-size: 0.68rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  @media (max-width: 700px) {
    .activity-section summary {
      gap: 0.85rem;
      padding: 1rem;
    }

    .activity-content {
      padding: 0 1rem 1rem;
    }

    .activity-columns {
      grid-template-columns: 1fr;
      gap: 1.35rem;
    }
  }
</style>
