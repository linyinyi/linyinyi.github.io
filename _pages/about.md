---
layout: about
title: About
permalink: /
subtitle: >
  <span class="yl-tagline">GeoAI and remote sensing for healthier, more resilient, and sustainable cities.</span><br>
  Postdoctoral Fellow, <a href="https://www.geog.hku.hk/">Department of Geography</a>, The University of Hong Kong

profile:
  align: right
  image: profile/yinyi-lin.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p><a href="mailto:yinyilin@hku.hk">yinyilin@hku.hk</a></p>

selected_papers: false # rendered manually below to control section order
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # rendered manually below to control section order
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
---

I am a geospatial scientist studying how urbanization and climate extremes shape environmental exposure, human health, and community resilience. My research integrates multisource satellite observations, environmental big data, spatial statistics, and artificial intelligence to produce high-resolution, policy-relevant evidence across cities and regions worldwide. I completed my PhD in Earth System and GeoInformation Science at The Chinese University of Hong Kong in 2021 and am now a Postdoctoral Fellow in Geography at The University of Hong Kong, where I work at the intersection of GeoAI, urban environmental health, climate risk, and sustainable urbanization.

<div class="yl-cta-row">
  <a class="yl-btn yl-btn-primary" href="/research/">View research</a>
  <a class="yl-btn" href="/publications/">Selected publications</a>
</div>

## Current research focus

<div class="yl-card-grid" role="list">
  {% for theme in site.data.research.themes %}
  <a class="yl-focus-card" role="listitem" href="{{ '/research/' | relative_url }}#{{ theme.slug }}">
    <h3>{{ theme.title }}</h3>
    <p>{{ theme.short }}</p>
    <span class="yl-card-more" aria-hidden="true">Read more →</span>
  </a>
  {% endfor %}
</div>

## Featured research

<div class="yl-feature-list">

  <article class="yl-feature-card">
    <div class="yl-feature-media">
      <img src="{{ '/assets/img/projects/project-heat-health.svg' | relative_url }}" alt="Stylized map of compound urban heat and air-pollution exposure across a city" loading="lazy">
    </div>
    <div class="yl-feature-body">
      <p class="yl-feature-meta"><span class="yl-status yl-status-published">Published</span> · Global North cities · satellite exposure mapping, structural equation modelling</p>
      <h3><a href="{{ '/projects/compound-heat-pollution-health/' | relative_url }}">Compound urban heat, air pollution, and mortality</a></h3>
      <p>How much mortality risk do cities miss when urban heat islands and air-pollution islands are assessed separately rather than together? This work quantifies compound heat–pollution islands across Global North cities and shows that their combined mortality burden is underestimated.</p>
      <p class="yl-feature-links"><a href="https://doi.org/10.1038/s42949-026-00411-3">Paper in <em>npj Urban Sustainability</em> (2026)</a></p>
    </div>
  </article>

  <article class="yl-feature-card">
    <div class="yl-feature-media">
      <img src="{{ '/assets/img/projects/project-urbanization.svg' | relative_url }}" alt="Stylized urban expansion motif with city blocks and radar scan lines" loading="lazy">
    </div>
    <div class="yl-feature-body">
      <p class="yl-feature-meta"><span class="yl-status yl-status-published">Published</span> · large-scale and multi-city · optical–SAR fusion, deep learning</p>
      <h3><a href="{{ '/projects/multisource-urbanization-monitoring/' | relative_url }}">Multisource urbanization monitoring</a></h3>
      <p>How can optical and radar observations be combined to map urban land cover and expansion reliably — through clouds, shadows, and seasons — over decades? This line of work established fusion methods for impervious-surface mapping, road extraction, and intra-year urban renewal detection.</p>
      <p class="yl-feature-links"><a href="{{ '/projects/multisource-urbanization-monitoring/' | relative_url }}">Project overview</a></p>
    </div>
  </article>

</div>

## Selected publications

<p class="yl-muted">Five representative studies; the full record is on the <a href="/publications/">publications page</a> and <a href="https://scholar.google.com/citations?user=5q5R47kAAAAJ&hl=en">Google Scholar</a>.</p>

{% include selected_papers.liquid %}

{% if site.data.metrics.enabled %}

## Research by the numbers

<div class="yl-metrics" role="list">
  {% for m in site.data.metrics.items %}
    {% if m.value %}
      <div class="yl-metric" role="listitem">
        <span class="yl-metric-value">{{ m.value }}</span>
        <span class="yl-metric-label">{{ m.label }}</span>
      </div>
    {% endif %}
  {% endfor %}
</div>
<p class="yl-muted">
  Source: {{ site.data.metrics.source }}, last verified {{ site.data.metrics.last_updated }}.
  Citation counts are dynamic and differ across databases.
</p>
{% endif %}

## Latest news

{% include news.liquid limit=true %}

<p><a href="/news/">All news →</a></p>
