---
layout: page
permalink: /publications/
title: publications
description: Journal articles, conference papers, and manuscripts under review in control systems and wind energy.
nav: true
nav_order: 2
---

<p class="pub-intro">
  Journal articles, peer-reviewed conference contributions, and manuscripts under review.
  Entries are listed in reverse chronological order within each category.
</p>

{% include bib_search.liquid %}

## Under Review

<div class="publications publications-clean">
{% bibliography --query @unpublished[website_status=under_review] --group_by none --sort_by year,month --order descending %}
</div>

## Journal Articles

<div class="publications publications-clean">
{% bibliography --query @article --group_by none --sort_by year,month --order descending %}
</div>

## Conference Papers

<div class="publications publications-clean">
{% bibliography --query @inproceedings --group_by none --sort_by year,month --order descending %}
</div>

<style>
  .pub-intro {
    max-width: 48rem;
    margin: 0.55rem 0 1.6rem;
    color: var(--global-text-color-light, #666);
    font-size: 0.94rem;
    line-height: 1.65;
  }

  .publications-clean {
    margin-bottom: 2.75rem;
  }

  .publications-clean ol.bibliography {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .publications-clean ol.bibliography > li {
    margin: 0;
    padding: 1.08rem 0 1.25rem;
    border-bottom: 1px solid var(--global-divider-color, #ddd);
    list-style: none;
  }

  .publications-clean ol.bibliography > li:first-child {
    padding-top: 0.3rem;
  }

  .publications-clean ol.bibliography > li:last-child {
    border-bottom: 0;
  }

  .publications-clean ol.bibliography > li > .row {
    margin-left: 0;
    margin-right: 0;
  }

  .publications-clean ol.bibliography > li > .row > [id] {
    flex: 0 0 100%;
    max-width: 100%;
    padding-left: 0;
    padding-right: 0;
  }

  .publications-clean .title {
    font-size: 1.02rem;
    font-weight: 650;
    line-height: 1.45;
    letter-spacing: -0.01em;
  }

  .publications-clean .author {
    font-size: 0.91rem;
    line-height: 1.55;
    margin-top: 0.27rem;
  }

  .publications-clean .periodical {
    margin-top: 0.18rem;
    font-size: 0.88rem;
    line-height: 1.5;
  }

  .publications-clean .periodical:empty {
    display: none;
  }

  .publications-clean .links {
    margin-top: 0.32rem;
  }

  @media (max-width: 600px) {
    .publications-clean ol.bibliography > li {
      padding-top: 1rem;
      padding-bottom: 1.05rem;
    }
  }
</style>
