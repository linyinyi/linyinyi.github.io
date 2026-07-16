---
layout: about
title: about
permalink: /
subtitle: >
  <span class="yl-tagline">GeoAI and remote sensing for healthier, more resilient, and sustainable cities.</span><br>
  Postdoctoral Fellow, <a href="https://www.geog.hku.hk/">Department of Geography</a>, The University of Hong Kong

profile:
  align: right
  image: profile/prof-pic-placeholder.svg # TODO: replace with a professional portrait, e.g. profile/prof-pic.jpg ([PROFILE_PHOTO_PATH])
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>Department of Geography</p>
    <p>The University of Hong Kong</p>
    <p>Hong Kong</p>

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
  <a class="yl-btn" href="/assets/rendercv/rendercv_output/Yinyi_Lin_CV.pdf">Download CV</a>
</div>

## current research focus

<div class="yl-card-grid" role="list">
  {% for theme in site.data.research.themes %}
  <a class="yl-focus-card" role="listitem" href="{{ '/research/' | relative_url }}#{{ theme.slug }}">
    <h3>{{ theme.title }}</h3>
    <p>{{ theme.short }}</p>
    <span class="yl-card-more" aria-hidden="true">Read more →</span>
  </a>
  {% endfor %}
</div>

## featured research

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
      <img src="{{ '/assets/img/projects/project-resilience.svg' | relative_url }}" alt="Stylized global grid map of community resilience to floods, droughts, and extreme temperatures" loading="lazy">
    </div>
    <div class="yl-feature-body">
      <p class="yl-feature-meta"><span class="yl-status yl-status-ongoing">Ongoing</span> · global gridded assessment · remote sensing, disaster records, random forest, fuzzy logic</p>
      <h3><a href="{{ '/projects/community-resilience-climate-extremes/' | relative_url }}">Community resilience to compound climate extremes</a></h3>
      <p>Which communities can absorb floods, droughts, and extreme temperatures — and which cannot? This project integrates satellite observations and disaster records to map community resilience at high resolution worldwide, and examines the inequalities the maps reveal.</p>
      <p class="yl-feature-links"><a href="{{ '/projects/community-resilience-climate-extremes/' | relative_url }}">Project overview</a></p>
    </div>
  </article>

  <article class="yl-feature-card">
    <div class="yl-feature-media">
      <img src="{{ '/assets/img/projects/project-ntl.svg' | relative_url }}" alt="Stylized nighttime-light intensity map of an urban region" loading="lazy">
    </div>
    <div class="yl-feature-body">
      <p class="yl-feature-meta"><span class="yl-status yl-status-ongoing">Ongoing</span> · urban and regional scale · monthly nighttime-light time series</p>
      <h3><a href="{{ '/projects/nighttime-light-resilience/' | relative_url }}">Community resilience from nighttime lights</a></h3>
      <p>Monthly nighttime-light observations record how places dim after climate and social shocks — and how quickly they brighten again. This project turns that longitudinal satellite signal into a measure of disturbance and recovery for cities and regions.</p>
      <p class="yl-feature-links"><a href="{{ '/projects/nighttime-light-resilience/' | relative_url }}">Project overview</a></p>
    </div>
  </article>

</div>

## selected publications

<p class="yl-muted">Five representative studies; the full record is on the <a href="/publications/">publications page</a> and <a href="https://scholar.google.com/citations?user=5q5R47kAAAAJ&hl=en">Google Scholar</a>.</p>

{% include selected_papers.liquid %}

{% if site.data.metrics.enabled %}

## research by the numbers

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

## latest news

{% include news.liquid limit=true %}

<p><a href="/news/">All news →</a></p>

## collaboration

I welcome conversations about research collaboration — particularly on GeoAI and remote sensing methods, urban environmental health, climate resilience, and sustainable urbanization — as well as interdisciplinary projects, joint grant proposals, and opportunities to mentor students. The best way to reach me is by <a href="mailto:yinyilin@hku.hk">email</a>; more options are on the <a href="/contact/">contact page</a>.
