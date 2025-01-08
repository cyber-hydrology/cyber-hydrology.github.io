---
title: "Gallery"
layout: default
permalink: /pictures/
---

# Picture Gallery

<div class="gallery">
  {% for image in site.data.gallery %}
    <div class="gallery-item">
      <img src="{{ site.baseurl }}/assets/images/{{ image.file }}" alt="{{ image.alt }}" class="gallery-image">
      <p>{{ image.caption }}</p>
    </div>
  {% endfor %}
</div>
