---
layout: default
title: Mehrab Hossain - Portfolio
permalink: /projects/
---
<style>
.gallery-item {
  height: auto !important;
  overflow: visible !important;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.gallery-item p {
  margin-top: 10px;
  text-align: center;
}
</style>
<div class="gallery-container">
<div class="project-gallery">
    {% for project in site.projects %}
      <div class="gallery-item">
        <a href="{{ project.url | relative_url }}">
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
          <p>{{ project.title}}</p>
        </a>
      </div>
    {% endfor %}
</div>
</div>