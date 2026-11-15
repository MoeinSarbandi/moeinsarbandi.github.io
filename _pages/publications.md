---
layout: page
permalink: /publications/
title: publications
description: Research papers, conference contributions, and manuscripts under review in automatic control and wind energy.
nav: true
nav_order: 2
---

{% include bib_search.liquid %}

<h2 class="pub-section-heading">Under Review</h2>
<div class="publications publications-compact" data-pub-prefix="P">
{% bibliography --template bib_compact --query @unpublished[website_status=under_review] --group_by none %}
</div>

<h2 class="pub-section-heading">Journal Papers</h2>
<div class="publications publications-compact" data-pub-prefix="J">
{% bibliography --template bib_compact --query @article --group_by none %}
</div>

<h2 class="pub-section-heading">Conference Papers</h2>
<div class="publications publications-compact" data-pub-prefix="C">
{% bibliography --template bib_compact --query @inproceedings --group_by none %}
</div>

<style>
  .pub-section-heading {
    margin: 1.65rem 0 0.55rem;
    padding-bottom: 0.25rem;
    border-bottom: 1px solid var(--global-divider-color, #ddd);
    font-size: 1.24rem;
    line-height: 1.3;
    font-weight: 650;
    color: var(--global-theme-color, #426bb4);
  }
  .pub-section-heading:first-of-type { margin-top: 1.15rem; }

  .publications-compact { margin: 0 0 0.85rem; }
  .publications-compact ol.bibliography {
    margin: 0 !important;
    padding: 0 0 0 1.65rem !important;
    list-style-type: square !important;
  }
  .publications-compact ol.bibliography > li {
    display: list-item !important;
    list-style-type: square !important;
    list-style-position: outside;
    margin: 0 0 0.34rem !important;
    padding: 0 !important;
    border: 0 !important;
    font-size: 0.96rem;
    line-height: 1.5;
  }
  .publications-compact ol.bibliography > li::marker {
    color: var(--global-text-color, #252525);
    font-size: 0.78em;
  }

  .publications-compact .pub-citation { display: inline; }
  .publications-compact .pub-marker {
    display: inline;
    margin-right: 0.38rem;
    white-space: nowrap;
    color: var(--global-text-color, #252525);
    font-family: Georgia, "Times New Roman", serif;
    font-size: 1em;
    font-weight: 400;
    font-style: normal;
    font-variant-numeric: lining-nums;
    vertical-align: baseline;
  }
  .publications-compact .pub-authors,
  .publications-compact .pub-title,
  .publications-compact .pub-venue {
    display: inline;
    margin: 0;
    padding: 0;
    font-size: inherit;
    line-height: inherit;
    font-weight: inherit;
  }
  .publications-compact .pub-authors strong {
    font-weight: 750;
    color: var(--global-text-color, #222);
  }
  .publications-compact .pub-title {
    color: var(--global-text-color, #222);
  }
  .publications-compact .pub-title a,
  .publications-compact .pub-title a:visited {
    color: #295A9B;
    text-decoration: none;
  }
  .publications-compact .pub-title a:hover,
  .publications-compact .pub-title a:focus-visible {
    color: #1D4477;
    text-decoration: underline;
    text-underline-offset: 2px;
  }
  .publications-compact .pub-venue em { font-style: italic; }
  .publications-compact .pub-title .btn,
  .publications-compact .pub-citation .links { display: none; }
  @media (max-width: 640px) {
    .publications-compact ol.bibliography { padding-left: 1.3rem !important; }
    .publications-compact ol.bibliography > li { font-size: 0.9rem; line-height: 1.5; margin-bottom: 0.55rem !important; }
    .pub-section-heading { font-size: 1.14rem; }
  }
</style>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.querySelectorAll(".publications-compact").forEach(function (section) {
      var prefix = section.getAttribute("data-pub-prefix") || "";
      var entries = section.querySelectorAll("ol.bibliography > li");
      entries.forEach(function (item, index) {
        var marker = item.querySelector(".pub-marker");
        if (marker) marker.textContent = "[" + prefix + (entries.length - index) + "]";
      });
    });
  });
</script>
