---
layout: page
permalink: /gallery-preview/
title: Gallery preview
description: An experimental, photo-first gallery layout for academic moments and research travel.
nav: false
sitemap: false
images:
  photoswipe: false
---

{% assign gv_event_count = 0 %}
{% assign gv_photo_count = 0 %}
{% assign gv_country_string = '' %}
{% for year_group in site.data.gallery %}
  {% assign gv_year_count = year_group.events | size %}
  {% assign gv_event_count = gv_event_count | plus: gv_year_count %}
  {% for event in year_group.events %}
    {% assign gv_n = event.photos | size %}
    {% assign gv_photo_count = gv_photo_count | plus: gv_n %}
    {% assign gv_country = event.location | split: ', ' | last %}
    {% assign gv_country_string = gv_country_string | append: gv_country | append: '|' %}
  {% endfor %}
{% endfor %}
{% assign gv_countries = gv_country_string | split: '|' | uniq | size %}
{% assign gv_first_year = site.data.gallery | last %}
{% assign gv_latest_year = site.data.gallery | first %}

<div class="gv" id="gv-preview">
  <div class="gv-preview-note" role="note">
    <span class="gv-preview-dot" aria-hidden="true"></span>
    <span>Design preview — your <a href="{{ '/gallery/' | relative_url }}">current gallery</a> is unchanged.</span>
  </div>

  <header class="gv-intro">
    <p class="gv-eyebrow">Conferences · People · Places</p>
    <h2>Research happens beyond the desk.</h2>
    <p class="gv-intro-copy">A visual diary of conferences, research visits, new ideas, and the people behind them. A few favourite moments, rather than a complete academic record.</p>
    <div class="gv-stats" aria-label="Gallery at a glance">
      <div><strong>{{ gv_event_count }}</strong><span>events</span></div>
      <div><strong>{{ gv_countries }}</strong><span>countries</span></div>
      <div><strong>{{ gv_photo_count }}</strong><span>photos</span></div>
      <div class="gv-stats-years"><strong>{{ gv_first_year.year }}–{{ gv_latest_year.year }}</strong><span>timeline</span></div>
    </div>
  </header>

  <div class="gv-toolbar">
    <div class="gv-filter-label">Explore the gallery</div>
    <nav class="gv-filters" aria-label="Filter gallery events">
      <button type="button" class="gv-filter is-selected" data-gv-filter="all" aria-pressed="true">All moments</button>
      <button type="button" class="gv-filter" data-gv-filter="talks" aria-pressed="false">Conferences & talks</button>
      <button type="button" class="gv-filter" data-gv-filter="workshops" aria-pressed="false">Workshops & courses</button>
      <button type="button" class="gv-filter" data-gv-filter="community" aria-pressed="false">Network & visits</button>
    </nav>
    <p class="gv-count" id="gv-visible-count" role="status" aria-live="polite">{{ gv_event_count }} events</p>
  </div>

  <div class="gv-years">
    {% for year_group in site.data.gallery %}
      <section class="gv-year" id="preview-year-{{ year_group.year }}" aria-labelledby="gv-title-{{ year_group.year }}">
        <div class="gv-year-heading">
          <h2 id="gv-title-{{ year_group.year }}">{{ year_group.year }}</h2>
          <span>{{ year_group.events | size }} moments</span>
        </div>
        <div class="gv-event-list">
          {% for event in year_group.events %}
            {% assign gv_group = 'community' %}
            {% if event.category == 'Conference' or event.category == 'Invited talk' or event.category == 'Scientific meeting' %}
              {% assign gv_group = 'talks' %}
            {% elsif event.category == 'Workshop' or event.category == 'Workshop and training' or event.category == 'Advanced course' %}
              {% assign gv_group = 'workshops' %}
            {% endif %}
            {% assign gv_photo_length = event.photos | size %}
            {% assign gv_hero_index = 0 %}
            {% if event.id == 'blocker-workshop-berlin' or event.id == 'dense-welcome-cottbus' %}
              {% assign gv_hero_index = 1 %}
            {% endif %}
            {% assign gv_hero = event.photos[gv_hero_index] %}
            <article class="gv-card" data-gv-group="{{ gv_group }}" id="preview-{{ event.id }}">
              <header class="gv-card-header">
                <div class="gv-card-topline">
                  <span class="gv-category">{{ event.category }}</span>
                  <span class="gv-date">{{ event.date }}</span>
                </div>
                <h3>{{ event.title }}</h3>
                <p class="gv-location"><i class="fa-solid fa-location-dot" aria-hidden="true"></i> {{ event.location }}</p>
                <p class="gv-role">{{ event.role }}</p>
              </header>

              {% if gv_photo_length > 0 %}
                <div class="gv-gallery" aria-label="Photos from {{ event.title | escape }}">
                  <a class="gv-photo gv-hero{% if gv_hero.height > gv_hero.width %} gv-hero-portrait{% endif %}"
                     href="{{ gv_hero.path | relative_url }}"
                     data-gv-caption="{{ gv_hero.alt | escape }}"
                     data-gv-event="{{ event.title | escape }}"
                     aria-label="View photo 1 of {{ gv_photo_length }}: {{ gv_hero.alt | escape }}">
                    <img src="{{ gv_hero.path | relative_url }}"
                         width="{{ gv_hero.width }}" height="{{ gv_hero.height }}"
                         alt="{{ gv_hero.alt | escape }}"
                         loading="lazy" decoding="async">
                    <span class="gv-expand" aria-hidden="true"><i class="fa-solid fa-expand"></i> View photo</span>
                  </a>
                  {% if gv_photo_length > 1 %}
                    <div class="gv-thumbnails" aria-label="More photos from this event">
                      {% for photo in event.photos %}
                        {% unless forloop.index0 == gv_hero_index %}
                          <a class="gv-photo gv-thumb"
                             href="{{ photo.path | relative_url }}"
                             data-gv-caption="{{ photo.alt | escape }}"
                             data-gv-event="{{ event.title | escape }}"
                             aria-label="View additional photo: {{ photo.alt | escape }}">
                            <img src="{{ photo.path | relative_url }}"
                                 width="{{ photo.width }}" height="{{ photo.height }}"
                                 alt="{{ photo.alt | escape }}"
                                 loading="lazy" decoding="async">
                            <span class="gv-thumb-zoom" aria-hidden="true"><i class="fa-solid fa-magnifying-glass-plus"></i></span>
                          </a>
                        {% endunless %}
                      {% endfor %}
                      <span class="gv-more-label">{{ gv_photo_length }} photos <i class="fa-solid fa-arrow-right" aria-hidden="true"></i></span>
                    </div>
                  {% endif %}
                </div>
              {% endif %}

              <div class="gv-card-bottom">
                <p class="gv-description">{{ event.description }}</p>
                {% if event.highlights %}
                  <details class="gv-details">
                    <summary>Highlights from this event</summary>
                    <ul>
                      {% for highlight in event.highlights %}
                        <li>{{ highlight }}</li>
                      {% endfor %}
                    </ul>
                  </details>
                {% endif %}
                <div class="gv-card-actions">
                  {% if event.url %}
                    <a href="{{ event.url }}" target="_blank" rel="noopener noreferrer">{{ event.url_label }} <span aria-hidden="true">↗</span></a>
                  {% endif %}
                  <a class="gv-event-permalink" href="#preview-{{ event.id }}" aria-label="Link to {{ event.title | escape }}">Event link <span aria-hidden="true">#</span></a>
                </div>
              </div>
            </article>
          {% endfor %}
        </div>
      </section>
    {% endfor %}
  </div>

  <div class="gv-end">
    <p>These are selected highlights. For a full list of lectures, presentations, and academic activities, see <a href="{{ '/activities/' | relative_url }}">Academic activities ↗</a>.</p>
    <a href="#gv-preview">Back to top ↑</a>
  </div>

  <dialog class="gv-lightbox" id="gv-lightbox" aria-label="Gallery photo viewer">
    <div class="gv-lightbox-shell">
      <div class="gv-lightbox-toolbar">
        <span class="gv-lightbox-event" id="gv-lightbox-event"></span>
        <span class="gv-lightbox-counter" id="gv-lightbox-counter"></span>
        <button type="button" class="gv-lightbox-close" id="gv-lightbox-close" aria-label="Close photo viewer">×</button>
      </div>
      <div class="gv-lightbox-stage" id="gv-lightbox-stage">
        <button type="button" class="gv-lightbox-arrow gv-lightbox-prev" id="gv-lightbox-prev" aria-label="Previous photo">‹</button>
        <img id="gv-lightbox-img" src="" alt="">
        <button type="button" class="gv-lightbox-arrow gv-lightbox-next" id="gv-lightbox-next" aria-label="Next photo">›</button>
      </div>
      <div class="gv-lightbox-caption" id="gv-lightbox-caption"></div>
      <p class="gv-lightbox-help">Swipe on mobile · Use ← → to browse · Esc to close</p>
    </div>
  </dialog>
</div>

<style>
  .gv { --gv-accent:var(--global-theme-color,#b509ac); --gv-border:var(--global-divider-color,#dddddd); --gv-muted:var(--global-text-color-light,#6c7077); --gv-panel:var(--global-bg-color,#fff); color:var(--global-text-color,#242424); max-width:100%; }
  .gv * { box-sizing:border-box; }
  .gv-preview-note { display:flex; align-items:center; gap:.65rem; padding:.7rem .95rem; margin:0 0 2rem; border:1px dashed var(--gv-border); border-radius:.6rem; font-size:.8rem; color:var(--gv-muted); }
  .gv-preview-note a { text-decoration:underline; text-underline-offset:3px; }
  .gv-preview-dot { flex:0 0 .5rem; width:.5rem; height:.5rem; border-radius:50%; background:var(--gv-accent); }
  .gv-intro { padding:.75rem 0 1.9rem; border-bottom:1px solid var(--gv-border); }
  .gv-eyebrow { font-size:.72rem; letter-spacing:.16em; text-transform:uppercase; font-weight:700; color:var(--gv-accent); margin:0 0 .8rem; }
  .gv-intro h2 { margin:0 0 .8rem; max-width:47rem; font-size:clamp(2rem,4.7vw,3.35rem); letter-spacing:-.045em; font-weight:650; line-height:1.12; }
  .gv-intro-copy { max-width:39rem; color:var(--gv-muted); font-size:clamp(.96rem,1.6vw,1.08rem); line-height:1.65; margin:0; }
  .gv-stats { display:flex; flex-wrap:wrap; gap:1.1rem clamp(1.3rem,4vw,2.7rem); padding-top:1.7rem; }
  .gv-stats > div { display:flex; align-items:baseline; gap:.4rem; }
  .gv-stats strong { font-size:clamp(1.2rem,2vw,1.55rem); font-weight:700; letter-spacing:-.035em; color:var(--global-text-color,#262626); }
  .gv-stats span { font-size:.82rem; color:var(--gv-muted); }
  .gv-stats-years { margin-left:auto; }
  .gv-toolbar { margin:1.75rem 0 2.35rem; }
  .gv-filter-label { margin-bottom:.75rem; text-transform:uppercase; letter-spacing:.11em; font-size:.71rem; color:var(--gv-muted); font-weight:700; }
  .gv-filters { display:flex; flex-wrap:wrap; gap:.5rem; }
  .gv-filter { cursor:pointer; border:1px solid var(--gv-border); border-radius:999px; padding:.48rem .85rem; background:transparent; color:var(--global-text-color,#242424); font-size:.82rem; line-height:1.2; font-weight:600; transition:background .15s,border-color .15s; }
  .gv-filter:hover,.gv-filter:focus-visible { border-color:var(--gv-accent); }
  .gv-filter.is-selected { border-color:var(--gv-accent); background:var(--gv-accent); color:#fff; }
  .gv-count { margin:.75rem 0 0; font-size:.77rem; color:var(--gv-muted); }
  .gv-year { scroll-margin-top:5rem; margin:0 0 3.6rem; }
  .gv-year[hidden],.gv-card[hidden] { display:none!important; }
  .gv-year-heading { display:flex; align-items:baseline; justify-content:space-between; border-bottom:1px solid var(--gv-border); margin:0 0 1.4rem; padding-bottom:.75rem; }
  .gv-year-heading h2 { margin:0; font-size:1.65rem; letter-spacing:-.03em; font-weight:650; }
  .gv-year-heading span { font-size:.82rem; color:var(--gv-muted); }
  .gv-event-list { display:grid; gap:2.05rem; }
  .gv-card { min-width:0; padding:clamp(1rem,3vw,1.55rem); border:1px solid var(--gv-border); border-radius:1rem; background:var(--gv-panel); box-shadow:0 .5rem 2rem rgba(0,0,0,.035); overflow:hidden; }
  .gv-card-topline { display:flex; flex-wrap:wrap; gap:.45rem .85rem; align-items:center; margin-bottom:.55rem; font-size:.75rem; }
  .gv-category { font-size:.69rem; font-weight:700; border-radius:999px; padding:.25rem .6rem; color:var(--gv-accent); background:color-mix(in srgb,var(--gv-accent) 10%,var(--gv-panel)); }
  .gv-date { color:var(--gv-muted); }
  .gv-card-header h3 { margin:0 0 .35rem; font-weight:650; font-size:clamp(1.22rem,2.3vw,1.65rem); line-height:1.25; letter-spacing:-.025em; }
  .gv-location { color:var(--gv-muted); margin:0 0 .4rem; font-size:.83rem; }
  .gv-location i { color:var(--gv-accent); margin-right:.25rem; }
  .gv-role { margin:0 0 1.15rem; font-weight:600; font-size:.86rem; }
  .gv-gallery { min-width:0; }
  .gv-photo { display:block; position:relative; overflow:hidden; background:color-mix(in srgb,var(--gv-border) 42%,var(--gv-panel)); }
  .gv-photo img { display:block; width:100%; height:100%; object-fit:cover; transition:transform .25s ease; }
  .gv-photo:hover img,.gv-photo:focus-visible img { transform:scale(1.025); }
  .gv-hero { width:100%; aspect-ratio:16/9; border-radius:.65rem; background:#25252b; }
  .gv-hero-portrait { aspect-ratio:3/2; }
  .gv-hero-portrait img { object-fit:contain; }
  .gv-expand { position:absolute; right:.8rem; bottom:.8rem; padding:.38rem .68rem; border-radius:999px; background:rgba(0,0,0,.72); font-size:.75rem; font-weight:600; color:#fff; display:flex; align-items:center; gap:.4rem; }
  .gv-thumbnails { display:flex; align-items:center; gap:.52rem; flex-wrap:wrap; margin-top:.55rem; }
  .gv-thumb { width:clamp(5.6rem,16%,8rem); aspect-ratio:3/2; border-radius:.45rem; flex:0 0 auto; }
  .gv-thumb-zoom { position:absolute; inset:0; display:flex; justify-content:center; align-items:center; color:white; background:rgba(0,0,0,.3); opacity:0; transition:opacity .15s; }
  .gv-thumb:hover .gv-thumb-zoom,.gv-thumb:focus-visible .gv-thumb-zoom { opacity:1; }
  .gv-more-label { margin-left:auto; display:flex; align-items:center; gap:.35rem; font-size:.74rem; white-space:nowrap; color:var(--gv-muted); }
  .gv-card-bottom { padding-top:1.1rem; }
  .gv-description { font-size:.91rem; line-height:1.65; margin:0 0 .75rem; }
  .gv-details { padding:.2rem 0 .4rem; }
  .gv-details summary { cursor:pointer; font-size:.82rem; color:var(--gv-accent); font-weight:600; }
  .gv-details ul { margin:.6rem 0; padding-left:1.35rem; font-size:.84rem; line-height:1.55; }
  .gv-details li+li { margin-top:.3rem; }
  .gv-card-actions { display:flex; align-items:center; flex-wrap:wrap; gap:.6rem 1.5rem; padding-top:.65rem; }
  .gv-card-actions a { text-decoration:none; font-size:.81rem; font-weight:650; }
  .gv-card-actions a:hover,.gv-card-actions a:focus-visible { text-decoration:underline; text-underline-offset:3px; }
  .gv-event-permalink { margin-left:auto; color:var(--gv-muted); }
  .gv-end { display:flex; justify-content:space-between; align-items:baseline; gap:1.5rem; padding:1.25rem 0 2rem; border-top:1px solid var(--gv-border); font-size:.84rem; color:var(--gv-muted); }
  .gv-end p { max-width:38rem; margin:0; }
  .gv-end > a { white-space:nowrap; }
  .gv-lightbox { box-sizing:border-box; width:min(96vw,1100px); max-width:none; max-height:96vh; padding:0; border:0; background:#16171b; color:#fff; border-radius:.75rem; overflow:hidden; }
  .gv-lightbox::backdrop { background:rgba(0,0,0,.90); }
  .gv-lightbox-shell { display:flex; flex-direction:column; max-height:96vh; }
  .gv-lightbox-toolbar { display:flex; align-items:center; gap:.75rem; padding:.75rem 1rem; min-height:3.2rem; }
  .gv-lightbox-event { font-size:.83rem; font-weight:600; overflow:hidden; text-overflow:ellipsis; white-space:nowrap; }
  .gv-lightbox-counter { margin-left:auto; font-size:.76rem; color:#bbb; white-space:nowrap; }
  .gv-lightbox-close { border:0; color:#fff; background:transparent; padding:.1rem .45rem; font-size:2rem; line-height:1; cursor:pointer; }
  .gv-lightbox-stage { position:relative; display:grid; place-items:center; min-height:10rem; overflow:hidden; }
  .gv-lightbox-stage img { display:block; max-width:100%; width:auto; height:auto; max-height:calc(96vh - 10rem); object-fit:contain; }
  .gv-lightbox-arrow { position:absolute; z-index:1; top:50%; transform:translateY(-50%); display:grid; place-items:center; border:0; width:2.65rem; height:2.65rem; border-radius:50%; color:#fff; background:rgba(0,0,0,.56); font-size:2rem; cursor:pointer; }
  .gv-lightbox-prev { left:.65rem; }
  .gv-lightbox-next { right:.65rem; }
  .gv-lightbox-arrow[disabled] { display:none; }
  .gv-lightbox-caption { color:#e0e0e0; font-size:.85rem; line-height:1.45; text-align:center; padding:.8rem 1.4rem .25rem; }
  .gv-lightbox-help { color:#999; font-size:.7rem; text-align:center; margin:.45rem 0 .8rem; }
  .gv button:focus-visible,.gv a:focus-visible,.gv summary:focus-visible { outline:3px solid var(--gv-accent); outline-offset:3px; }
  @media(max-width:650px) {
    .gv-intro h2 { font-size:2.1rem; }
    .gv-stats { gap:.7rem 1.3rem; }
    .gv-stats-years { margin-left:0; }
    .gv-event-list { gap:1.3rem; }
    .gv-hero { aspect-ratio:4/3; }
    .gv-hero-portrait { aspect-ratio:1/1; }
    .gv-more-label { font-size:.68rem; }
    .gv-card { padding:.9rem; }
    .gv-end { flex-direction:column; gap:.6rem; }
    .gv-lightbox { width:100vw; max-height:100dvh; height:100dvh; border-radius:0; }
    .gv-lightbox-shell { max-height:100dvh; height:100dvh; justify-content:center; }
    .gv-lightbox-stage img { max-height:calc(100dvh - 12rem); }
    .gv-lightbox-toolbar { position:absolute; top:0; left:0; right:0; z-index:2; background:#16171b; }
    .gv-lightbox-prev { left:.3rem; }
    .gv-lightbox-next { right:.3rem; }
  }
  @media(prefers-reduced-motion:reduce) {
    .gv-filter,.gv-photo img,.gv-thumb-zoom { transition:none; }
  }
</style>

<script>
(function () {
  function initGalleryPreview() {
    var root = document.getElementById('gv-preview');
    if (!root || root.dataset.initialized === 'true') return;
    root.dataset.initialized = 'true';

    var filters = Array.prototype.slice.call(root.querySelectorAll('[data-gv-filter]'));
    var cards = Array.prototype.slice.call(root.querySelectorAll('.gv-card'));
    var years = Array.prototype.slice.call(root.querySelectorAll('.gv-year'));
    var countText = document.getElementById('gv-visible-count');

    filters.forEach(function (button) {
      button.addEventListener('click', function () {
        var chosen = button.getAttribute('data-gv-filter');
        var visible = 0;
        filters.forEach(function (item) {
          var selected = item === button;
          item.classList.toggle('is-selected', selected);
          item.setAttribute('aria-pressed', selected ? 'true' : 'false');
        });
        cards.forEach(function (card) {
          var show = chosen === 'all' || card.getAttribute('data-gv-group') === chosen;
          card.hidden = !show;
          if (show) visible++;
        });
        years.forEach(function (year) {
          year.hidden = !year.querySelector('.gv-card:not([hidden])');
        });
        if (countText) countText.textContent = visible + (visible === 1 ? ' event' : ' events');
      });
    });

    var dialog = document.getElementById('gv-lightbox');
    if (!dialog || typeof dialog.showModal !== 'function') return;
    var viewerImage = document.getElementById('gv-lightbox-img');
    var viewerCaption = document.getElementById('gv-lightbox-caption');
    var viewerEvent = document.getElementById('gv-lightbox-event');
    var viewerCounter = document.getElementById('gv-lightbox-counter');
    var viewerStage = document.getElementById('gv-lightbox-stage');
    var prevButton = document.getElementById('gv-lightbox-prev');
    var nextButton = document.getElementById('gv-lightbox-next');
    var closeButton = document.getElementById('gv-lightbox-close');
    var activePhotos = [];
    var activeIndex = 0;

    function showPhoto(index) {
      if (!activePhotos.length) return;
      activeIndex = (index + activePhotos.length) % activePhotos.length;
      var anchor = activePhotos[activeIndex];
      viewerImage.src = anchor.href;
      viewerImage.alt = anchor.querySelector('img').alt;
      viewerCaption.textContent = anchor.getAttribute('data-gv-caption') || viewerImage.alt;
      viewerEvent.textContent = anchor.getAttribute('data-gv-event') || 'Gallery';
      viewerCounter.textContent = (activeIndex + 1) + ' / ' + activePhotos.length;
      prevButton.disabled = activePhotos.length < 2;
      nextButton.disabled = activePhotos.length < 2;
    }

    root.querySelectorAll('a.gv-photo').forEach(function (anchor) {
      anchor.addEventListener('click', function (e) {
        var gallery = anchor.closest('.gv-gallery');
        if (!gallery) return;
        e.preventDefault();
        activePhotos = Array.prototype.slice.call(gallery.querySelectorAll('a.gv-photo'));
        showPhoto(activePhotos.indexOf(anchor));
        dialog.showModal();
        closeButton.focus();
      });
    });

    prevButton.addEventListener('click', function () { showPhoto(activeIndex - 1); });
    nextButton.addEventListener('click', function () { showPhoto(activeIndex + 1); });
    closeButton.addEventListener('click', function () { dialog.close(); });
    dialog.addEventListener('click', function (e) { if (e.target === dialog) dialog.close(); });
    dialog.addEventListener('close', function () { viewerImage.removeAttribute('src'); });
    dialog.addEventListener('keydown', function (e) {
      if (e.key === 'ArrowLeft' && activePhotos.length > 1) { e.preventDefault(); showPhoto(activeIndex - 1); }
      if (e.key === 'ArrowRight' && activePhotos.length > 1) { e.preventDefault(); showPhoto(activeIndex + 1); }
    });

    var touchX = null;
    var touchY = null;
    viewerStage.addEventListener('touchstart', function (e) {
      if (e.touches.length !== 1) return;
      touchX = e.touches[0].clientX;
      touchY = e.touches[0].clientY;
    }, { passive: true });
    viewerStage.addEventListener('touchend', function (e) {
      if (touchX === null || !e.changedTouches.length) return;
      var deltaX = e.changedTouches[0].clientX - touchX;
      var deltaY = e.changedTouches[0].clientY - touchY;
      touchX = null;
      touchY = null;
      if (Math.abs(deltaX) > 45 && Math.abs(deltaX) > Math.abs(deltaY) * 1.3 && activePhotos.length > 1) {
        showPhoto(activeIndex + (deltaX < 0 ? 1 : -1));
      }
    }, { passive: true });
  }
  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', initGalleryPreview);
  } else {
    initGalleryPreview();
  }
}());
</script>
