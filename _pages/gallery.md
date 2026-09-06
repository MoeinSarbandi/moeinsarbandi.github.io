---
layout: page
permalink: /gallery/
title: gallery
description: Selected moments from conferences, workshops, research visits, and the academic community.
nav: true
nav_order: 6
images:
  photoswipe: true
---

<div class="gallery-intro">
  <p class="gallery-intro-kicker">Academic highlights · 2025–2026</p>
  <p class="gallery-intro-lead">
    Selected moments from research presentations, doctoral-network meetings, advanced courses, and international collaborations.
    This is a visual complement to my <a href="{{ '/activities/' | relative_url }}">academic activities</a>, not a complete record.
  </p>
  <div class="gallery-topics" aria-label="Gallery topics">
    <span>Conferences</span>
    <span>Workshops</span>
    <span>Research visits</span>
    <span>Community</span>
  </div>
</div>

<nav class="gallery-year-nav" aria-label="Gallery years">
  <span>Browse by year</span>
  {% for year_group in site.data.gallery %}
    <a href="#year-{{ year_group.year }}">{{ year_group.year }}</a>
  {% endfor %}
</nav>

<div class="academic-gallery">
  {% for year_group in site.data.gallery %}
    <section class="gallery-year" id="year-{{ year_group.year }}">
      <header class="gallery-year-heading">
        <h2>{{ year_group.year }}</h2>
        <span>{{ year_group.events | size }} highlights</span>
      </header>

      <div class="gallery-events">
        {% for event in year_group.events %}
          {% assign photo_count = event.photos | size %}
          <article class="gallery-event" id="{{ event.id }}">
            <div class="gallery-event-copy">
              <div class="gallery-event-meta">
                <span class="gallery-event-category">{{ event.category }}</span>
                <span>{{ event.date }}</span>
              </div>
              <h3>{{ event.title }}</h3>
              <p class="gallery-event-location"><i class="fa-solid fa-location-dot" aria-hidden="true"></i>{{ event.location }}</p>
              <p class="gallery-event-role">{{ event.role }}</p>
              <p>{{ event.description }}</p>
              {% if event.url %}
                <a class="gallery-event-link" href="{{ event.url }}" target="_blank" rel="noopener noreferrer">
                  {{ event.url_label }} <i class="fa-solid fa-arrow-up-right-from-square" aria-hidden="true"></i>
                </a>
              {% endif %}
            </div>

            <div class="gallery-event-media pswp-gallery gallery-count-{{ photo_count }}" id="gallery-{{ event.id }}">
              {% for photo in event.photos %}
                <a
                  href="{{ photo.path | relative_url }}"
                  data-pswp-width="{{ photo.width }}"
                  data-pswp-height="{{ photo.height }}"
                  target="_blank"
                  aria-label="Open image: {{ photo.alt }}"
                >
                  <img
                    src="{{ photo.path | relative_url }}"
                    width="{{ photo.width }}"
                    height="{{ photo.height }}"
                    alt="{{ photo.alt }}"
                    loading="lazy"
                    decoding="async"
                  >
                  <span class="gallery-zoom" aria-hidden="true"><i class="fa-solid fa-expand"></i></span>
                </a>
              {% endfor %}
            </div>
          </article>
        {% endfor %}
      </div>
    </section>

{% endfor %}

</div>

<p class="gallery-footnote">
  This gallery is intentionally selective. Additional talks and presentations are listed under
  <a href="{{ '/activities/' | relative_url }}">academic activities</a>.
</p>

<style>
  .gallery-intro {
    margin: 0.75rem 0 2rem;
    padding: clamp(1.25rem, 4vw, 2.25rem);
    border: 1px solid color-mix(in srgb, var(--global-theme-color, #b509ac) 24%, var(--global-divider-color, #d7d7d7));
    border-radius: 1rem;
    background:
      radial-gradient(circle at 92% 8%, color-mix(in srgb, var(--global-theme-color, #b509ac) 12%, transparent), transparent 34%),
      var(--global-bg-color, #fff);
  }

  .gallery-intro-kicker {
    margin: 0 0 0.45rem;
    color: var(--global-theme-color, #b509ac);
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .gallery-intro-lead {
    max-width: 48rem;
    margin: 0;
    font-size: clamp(1.05rem, 2vw, 1.25rem);
    line-height: 1.65;
  }

  .gallery-topics {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1.25rem;
  }

  .gallery-topics span {
    padding: 0.35rem 0.7rem;
    border: 1px solid var(--global-divider-color, #d7d7d7);
    border-radius: 999px;
    color: var(--global-text-color-light, #666);
    font-size: 0.78rem;
  }

  .gallery-year-nav {
    display: flex;
    align-items: center;
    gap: 0.65rem;
    margin-bottom: 2.75rem;
    color: var(--global-text-color-light, #666);
    font-size: 0.85rem;
  }

  .gallery-year-nav a {
    padding: 0.3rem 0.7rem;
    border-radius: 999px;
    background: color-mix(in srgb, var(--global-theme-color, #b509ac) 9%, var(--global-bg-color, #fff));
    font-weight: 600;
  }

  .gallery-year {
    scroll-margin-top: 5rem;
  }

  .gallery-year + .gallery-year {
    margin-top: 4.5rem;
  }

  .gallery-year-heading {
    display: flex;
    align-items: baseline;
    gap: 1rem;
    margin-bottom: 1.5rem;
    border-bottom: 1px solid var(--global-divider-color, #d7d7d7);
  }

  .gallery-year-heading h2 {
    margin: 0;
    padding-bottom: 0.55rem;
    border-bottom: 3px solid var(--global-theme-color, #b509ac);
    font-size: clamp(2rem, 5vw, 3.25rem);
    font-weight: 500;
    line-height: 1;
  }

  .gallery-year-heading span {
    color: var(--global-text-color-light, #666);
    font-size: 0.82rem;
  }

  .gallery-events {
    display: grid;
    gap: 1.5rem;
  }

  .gallery-event {
    display: grid;
    grid-template-columns: minmax(16rem, 0.78fr) minmax(0, 1.35fr);
    gap: clamp(1.2rem, 3vw, 2rem);
    padding: clamp(1rem, 2.5vw, 1.5rem);
    border: 1px solid var(--global-divider-color, #d7d7d7);
    border-radius: 1rem;
    background: var(--global-bg-color, #fff);
    box-shadow: 0 0.65rem 1.8rem rgba(0, 0, 0, 0.055);
  }

  .gallery-event-copy {
    align-self: center;
  }

  .gallery-event-meta {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.5rem 0.75rem;
    margin-bottom: 0.55rem;
    color: var(--global-text-color-light, #666);
    font-size: 0.78rem;
  }

  .gallery-event-category {
    padding: 0.23rem 0.58rem;
    border-radius: 999px;
    background: color-mix(in srgb, var(--global-theme-color, #b509ac) 12%, var(--global-bg-color, #fff));
    color: var(--global-theme-color, #b509ac);
    font-weight: 700;
  }

  .gallery-event h3 {
    margin: 0 0 0.55rem;
    font-size: clamp(1.28rem, 2.6vw, 1.8rem);
    font-weight: 600;
    line-height: 1.25;
  }

  .gallery-event-copy > p {
    font-size: 0.92rem;
    line-height: 1.6;
  }

  .gallery-event-location {
    display: flex;
    gap: 0.45rem;
    margin: 0 0 0.2rem;
    color: var(--global-text-color-light, #666);
  }

  .gallery-event-location i {
    margin-top: 0.28rem;
    color: var(--global-theme-color, #b509ac);
    font-size: 0.78rem;
  }

  .gallery-event-role {
    margin: 0 0 0.85rem;
    font-weight: 600;
  }

  .gallery-event-link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    margin-top: 0.25rem;
    font-size: 0.86rem;
    font-weight: 600;
  }

  .gallery-event-link i {
    font-size: 0.7rem;
  }

  .gallery-event-media {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 0.55rem;
    min-width: 0;
  }

  .gallery-event-media > a {
    position: relative;
    min-height: 10rem;
    overflow: hidden;
    border-radius: 0.7rem;
    background: color-mix(in srgb, var(--global-divider-color, #d7d7d7) 65%, var(--global-bg-color, #fff));
  }

  .gallery-event-media img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 220ms ease;
  }

  .gallery-event-media > a:hover img,
  .gallery-event-media > a:focus-visible img {
    transform: scale(1.025);
  }

  .gallery-count-1 > a {
    grid-column: 1 / -1;
    aspect-ratio: 16 / 10;
  }

  .gallery-count-2 > a {
    aspect-ratio: 4 / 5;
  }

  .gallery-event-media:not(.gallery-count-1):not(.gallery-count-2) > a:first-child {
    grid-column: 1 / -1;
    aspect-ratio: 16 / 8;
  }

  .gallery-event-media:not(.gallery-count-1):not(.gallery-count-2) > a:not(:first-child) {
    aspect-ratio: 4 / 3;
  }

  .gallery-zoom {
    position: absolute;
    right: 0.55rem;
    bottom: 0.55rem;
    display: grid;
    width: 1.8rem;
    height: 1.8rem;
    place-items: center;
    border-radius: 50%;
    background: rgba(0, 0, 0, 0.62);
    color: #fff;
    font-size: 0.72rem;
    opacity: 0;
    transition: opacity 160ms ease;
  }

  .gallery-event-media > a:hover .gallery-zoom,
  .gallery-event-media > a:focus-visible .gallery-zoom {
    opacity: 1;
  }

  .gallery-footnote {
    margin-top: 3rem;
    padding-top: 1.25rem;
    border-top: 1px solid var(--global-divider-color, #d7d7d7);
    color: var(--global-text-color-light, #666);
    font-size: 0.88rem;
  }

  @media (max-width: 820px) {
    .gallery-event {
      grid-template-columns: 1fr;
    }

    .gallery-event-media {
      order: -1;
    }

    .gallery-count-1 > a {
      aspect-ratio: 4 / 3;
    }
  }

  @media (max-width: 480px) {
    .gallery-year-nav > span {
      display: none;
    }

    .gallery-event-media > a,
    .gallery-count-2 > a,
    .gallery-event-media:not(.gallery-count-1):not(.gallery-count-2) > a:first-child {
      grid-column: 1 / -1;
      aspect-ratio: 4 / 3;
      min-height: 0;
    }

    .gallery-event-media:not(.gallery-count-1):not(.gallery-count-2) > a:not(:first-child) {
      aspect-ratio: 4 / 3;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .gallery-event-media img,
    .gallery-zoom {
      transition: none;
    }
  }
</style>
