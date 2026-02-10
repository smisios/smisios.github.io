---
layout: page
title: gallery
description: a selection of photos I took during my travels! for full quality pictures, contact me.
permalink: /gallery/
nav: true
nav_order: 5
---

<div class="gallery">
  {% for image in site.data.gallery %}
    <div class="gallery-item">
      <a href="{{ '/assets/img/gallery/' | append: image.url | relative_url }}" 
         class="gallery-item glightbox" 
         data-title="{{ image.title }}" 
         data-description="{{ image.caption }}">
        <img src="{{ '/assets/img/gallery/' | append: image.url | relative_url }}" alt="{{ image.title }}">
      </a>
    </div>
  {% endfor %}
</div>

<link href="https://cdn.jsdelivr.net/npm/glightbox/dist/css/glightbox.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/glightbox/dist/js/glightbox.min.js"></script>
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const lightbox = GLightbox({
      selector: '.glightbox',
      skin: 'clean',
      touchNavigation: true,
      loop: true,
      openEffect: 'zoom',
      closeEffect: 'zoom',
      slideEffect: 'slide',
      descPosition: 'left',
      zoomable: false,
      autoplayVideos: false,
      moreLength: 60,
      moreText: 'See more'
    });
  });
</script>

<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 0.5rem;
  }

  .gallery-item {
    display: block;
  }

  .gallery-item img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    transition: transform 0.3s ease;
  }

  .gallery-item:hover img {
    transform: scale(1.03);
  }

  .glightbox-clean .gslide-description .gdesc-inner {
    color: #3d3c42;
  }

  .glightbox-clean .gslide-title {
    font-weight: bold;
    color: #3d3c42;
  }

  @media (min-width: 768px) {
    html[data-theme="dark"] .glightbox-clean .gslide-description .gdesc-inner {
      color: #f1ddd8;
      background: #26282e;
    }
    html[data-theme="dark"] .glightbox-clean .gslide-title {
      color: #f1ddd8;
      font-weight: bold;
    }
  }

  .gdesc-inner {
    width: 100%;
    box-sizing: border-box;
  }

  .glightbox-container {
    background: rgba(0, 0, 0, 0.8);
  }

  /* Title in the lightbox */
  .glightbox-clean .gslide-title {
    font-family: var(--bs-body-font-family, "Lato", system-ui, sans-serif);
    font-weight: bold;
    font-size: 1.1rem;
  }

  /* Description/caption in the lightbox */
  .glightbox-clean .gslide-description .gdesc-inner {
    font-family: var(--bs-body-font-family, "Lato", system-ui, sans-serif);
    font-weight: 200;
    font-size: 0.95rem;
    line-height: 1.4;
  }
</style>
