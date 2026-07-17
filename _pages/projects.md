---
layout: page
title: Projects
permalink: /projects/
description: Research projects spanning GeoAI methods, urban environmental health, and sustainable urbanization.
nav: false # hidden from the navigation; set to true to restore the Projects tab
nav_order: 3
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">

<!-- Display projects without categories, ordered by `importance` -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
</div>
