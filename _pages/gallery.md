---

layout: page

title: gallery

description: a selection of photos I took during my travels!

permalink: /gallery/

nav: true

nav_order: 5

---

<div class="gallery">

  {% for image in site.data.gallery %}

    <figure class="gallery-item">

      <a 

        href="{{ '/assets/img/gallery/' | append: image.url | relative_url }}"

        class="glightbox"

        data-title="{{ image.title | escape }}"

        data-description="{{ image.caption | escape }}"

      >

        <img 

          src="{{ '/assets/img/gallery/' | append: image.url | relative_url }}"

          alt="{{ image.title | escape }}"

          loading="lazy"

        >

      </a>

    </figure>

  {% endfor %}

</div>

<!-- GLightbox -->

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/glightbox/dist/css/glightbox.min.css">

<script src="https://cdn.jsdelivr.net/npm/glightbox/dist/js/glightbox.min.js"></script>

<script>

document.addEventListener("DOMContentLoaded", function () {

  GLightbox({

    selector: '.glightbox',

    touchNavigation: true,

    loop: true,

    openEffect: 'zoom',

    closeEffect: 'zoom',

    slideEffect: 'slide',

    descPosition: 'bottom',

    zoomable: false,

    autoplayVideos: false

  });

});

</script>

<style>

/* ─── GRID ─── */

.gallery {

  display: grid;

  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  gap: 0.6rem;

}

/* ─── ITEM ─── */

.gallery-item {

  margin: 0;

}

/* ─── IMAGE ─── */

.gallery-item img {

  width: 100%;

  height: 220px;

  object-fit: cover;

  border-radius: 10px;

  transition: transform 0.25s ease, box-shadow 0.25s ease;

}

/* Hover */

.gallery-item:hover img {

  transform: scale(1.04);

  box-shadow: 0 6px 18px rgba(0,0,0,0.25);

}

/* ─── LIGHTBOX ─── */

.glightbox-container {

  background: rgba(0, 0, 0, 0.85);

}

/* Title */

.glightbox-clean .gslide-title {

  font-family: var(--bs-body-font-family, system-ui);

  font-weight: 600;

  font-size: 1.1rem;

}

/* Caption */

.glightbox-clean .gdesc-inner {

  font-family: var(--bs-body-font-family, system-ui);

  font-size: 0.95rem;

  line-height: 1.5;

}

/* ─── DARK MODE ─── */

html[data-theme="dark"] .glightbox-clean .gslide-title,

html[data-theme="dark"] .glightbox-clean .gdesc-inner {

  color: #f1ddd8;

}

html[data-theme="dark"] .gdesc-inner {

  background: #26282e;

}

</style>