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
          <article class="gallery-event{% if photo_count == 0 %} gallery-event-text-only{% endif %}" id="{{ event.id }}">
            <div class="gallery-event-copy">
              <div class="gallery-event-meta">
                <span class="gallery-event-category">{{ event.category }}</span>
                <span>{{ event.date }}</span>
              </div>
              <h3>{{ event.title }}</h3>
              <p class="gallery-event-location"><i class="fa-solid fa-location-dot" aria-hidden="true"></i>{{ event.location }}</p>
              <p class="gallery-event-role">{{ event.role }}</p>
              <p class="gallery-event-description" id="gallery-description-{{ event.id }}">{{ event.description }}</p>
              <button
                type="button"
                class="gallery-description-toggle"
                aria-controls="gallery-description-{{ event.id }}"
                aria-expanded="false"
                hidden
              >Read more <span aria-hidden="true">↓</span></button>
              {% if event.highlights %}
                <details class="gallery-event-details">
                  <summary>Event highlights <span class="gallery-event-highlights-count">({{ event.highlights | size }})</span></summary>
                  <ul class="gallery-event-highlights">
                    {% for highlight in event.highlights %}
                      <li>{{ highlight }}</li>
                    {% endfor %}
                  </ul>
                </details>
              {% endif %}
              {% if event.url %}
                <a class="gallery-event-link" href="{{ event.url }}" target="_blank" rel="noopener noreferrer">
                  {{ event.url_label }} <i class="fa-solid fa-arrow-up-right-from-square" aria-hidden="true"></i>
                </a>
              {% endif %}
            </div>

            {% if photo_count > 0 %}
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
            {% endif %}
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
    min-height: 23rem;
    gap: clamp(1.2rem, 3vw, 2rem);
    padding: clamp(1rem, 2.5vw, 1.5rem);
    border: 1px solid var(--global-divider-color, #d7d7d7);
    border-radius: 1rem;
    background: var(--global-bg-color, #fff);
    box-shadow: 0 0.65rem 1.8rem rgba(0, 0, 0, 0.055);
  }

  .gallery-event-text-only {
    grid-template-columns: minmax(0, 1fr);
  }

  .gallery-event-text-only .gallery-event-copy {
    max-width: 48rem;
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

  /* JavaScript activates the clamp only when text actually overflows.
     If JavaScript is unavailable, all descriptions remain readable. */
  .gallery-event-description.is-clamped {
    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gallery-description-toggle:not([hidden]) {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    padding: 0;
    margin: -0.2rem 0 0.8rem;
    border: 0;
    background: transparent;
    color: var(--global-theme-color, #b509ac);
    font: inherit;
    font-size: 0.84rem;
    font-weight: 600;
    cursor: pointer;
  }

  .gallery-description-toggle:focus-visible,
  .gallery-event-details summary:focus-visible {
    outline: 2px solid var(--global-theme-color, #b509ac);
    outline-offset: 4px;
    border-radius: 0.15rem;
  }

  .gallery-event-details {
    margin: 0.75rem 0 0.9rem;
    padding-top: 0.65rem;
    border-top: 1px solid var(--global-divider-color, #d7d7d7);
  }

  .gallery-event-details summary {
    color: var(--global-theme-color, #b509ac);
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
  }

  .gallery-event-highlights-count {
    color: var(--global-text-color-light, #666);
    font-weight: 400;
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

  .gallery-event-highlights {
    margin: 0.75rem 0 0.2rem;
    padding-left: 1.15rem;
    font-size: 0.9rem;
    line-height: 1.5;
  }

  .gallery-event-highlights li + li {
    margin-top: 0.35rem;
  }

  .gallery-event-highlights li::marker {
    color: var(--global-theme-color, #b509ac);
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
    grid-template-columns: repeat(4, minmax(0, 1fr));
    align-content: start;
    gap: 0.5rem;
    min-width: 0;
  }

  .gallery-event-media > a {
    position: relative;
    min-width: 0;
    min-height: 0;
    aspect-ratio: 4 / 3;
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

  /* Keep single-photo events exactly as before. */
  .gallery-count-1 > a:first-child {
    grid-column: 1 / -1;
    aspect-ratio: 16 / 10;
  }

  /* For multi-photo events, feature one reasonably sized photo on top.
     All remaining photos form a compact thumbnail strip beneath it. */
  .gallery-event-media:not(.gallery-count-1) > a:first-child {
    grid-column: 1 / -1;
    aspect-ratio: 16 / 9;
    max-height: 20rem;
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
      min-height: 0;
    }

    .gallery-event-media {
      order: -1;
    }

    .gallery-count-1 > a:first-child {
      aspect-ratio: 4 / 3;
    }
  }

  @media (max-width: 480px) {
    .gallery-year-nav > span {
      display: none;
    }

    .gallery-event-media {
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }

    .gallery-event-media > a:first-child {
      grid-column: 1 / -1;
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

<script>
  (function () {
    function initGalleryDescriptions() {
      document.querySelectorAll('.academic-gallery .gallery-event').forEach(function (card) {
        var description = card.querySelector('.gallery-event-description');
        var button = card.querySelector('.gallery-description-toggle');
        if (!description || !button) return;

        // Only show the control when the paragraph exceeds four rendered lines.
        // Keep the full content in the DOM for accessibility and no-JS fallback.
        function measure() {
          var expanded = button.getAttribute('aria-expanded') === 'true';
          if (expanded) return;
          description.classList.remove('is-clamped');
          var fullHeight = description.getBoundingClientRect().height;
          description.classList.add('is-clamped');
          var shortHeight = description.getBoundingClientRect().height;
          var overflowing = fullHeight > shortHeight + 2;
          if (!overflowing) description.classList.remove('is-clamped');
          button.hidden = !overflowing;
          button.setAttribute('aria-expanded', 'false');
        }

        button.addEventListener('click', function () {
          var expanded = button.getAttribute('aria-expanded') === 'true';
          description.classList.toggle('is-clamped', expanded);
          button.setAttribute('aria-expanded', expanded ? 'false' : 'true');
          button.innerHTML = expanded
            ? 'Read more <span aria-hidden="true">↓</span>'
            : 'Show less <span aria-hidden="true">↑</span>';
        });

        measure();
        if (typeof ResizeObserver !== 'undefined') {
          var observer = new ResizeObserver(function () {
            measure();
          });
          observer.observe(card.querySelector('.gallery-event-copy'));
        } else {
          window.addEventListener('resize', measure, { passive: true });
        }
      });
    }

    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', initGalleryDescriptions);
    } else {
      initGalleryDescriptions();
    }
  })();
</script>
