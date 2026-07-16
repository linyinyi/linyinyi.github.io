---
layout: page
permalink: /research/
title: research
description: Four connected research themes — GeoAI and multisource remote sensing, urban environmental health, climate risk and community resilience, and sustainable urbanization.
nav: true
nav_order: 1
---

My research program asks a single connected question: **how do urbanization, climate extremes, and environmental inequality shape human health, community resilience, and sustainable development — and how can satellite observation and geospatial artificial intelligence answer that question at the scales where decisions are made?**

The four themes below build on one another. Methods developed under GeoAI and multisource remote sensing supply the exposure and land-change evidence used in the three applied themes.

<div class="yl-diagram" role="img" aria-label="Conceptual diagram: Earth observation feeds GeoAI and spatial modelling, which quantifies environmental exposure and climate shocks, which are linked to health and resilience outcomes, which inform policy and adaptation.">
  <div class="yl-diagram-step">Earth<br>observation</div>
  <div class="yl-diagram-arrow" aria-hidden="true">→</div>
  <div class="yl-diagram-step">GeoAI &amp;<br>spatial modelling</div>
  <div class="yl-diagram-arrow" aria-hidden="true">→</div>
  <div class="yl-diagram-step">Environmental exposure<br>&amp; climate shocks</div>
  <div class="yl-diagram-arrow" aria-hidden="true">→</div>
  <div class="yl-diagram-step">Health &amp; resilience<br>outcomes</div>
  <div class="yl-diagram-arrow" aria-hidden="true">→</div>
  <div class="yl-diagram-step">Policy &amp;<br>adaptation</div>
</div>

{% for theme in site.data.research.themes %}

<section class="yl-theme" id="{{ theme.slug }}">
  <div class="yl-theme-header">
    <h2>{{ theme.title }}</h2>
  </div>
  <div class="yl-theme-grid">
    <div class="yl-theme-text">
      <p>{{ theme.summary }}</p>
      <h3 class="yl-theme-subhead">Key questions</h3>
      <ul>
        {% for q in theme.questions %}<li>{{ q }}</li>{% endfor %}
      </ul>
      <p><strong>Methods.</strong> {{ theme.methods }}</p>
      <p><strong>Scale.</strong> {{ theme.scale }}</p>
      <p class="yl-keywords" aria-label="Keywords">
        {% for kw in theme.keywords %}<span class="yl-keyword">{{ kw }}</span>{% endfor %}
      </p>
    </div>
    <div class="yl-theme-media">
      <img src="{{ theme.image | relative_url }}" alt="" loading="lazy">
      <p class="yl-muted yl-caption">Illustrative motif — replace with a study figure in <code>assets/img/research/</code>.</p>
    </div>
  </div>
  <h3 class="yl-theme-subhead">Selected publications</h3>
  <div class="publications">
    {% capture bibquery %}@*[keywords~={{ theme.bibfilter }}]*{% endcapture %}
    {% bibliography --group_by none --max 3 --query {{ bibquery }} %}
  </div>
  <p><a href="{{ '/publications/' | relative_url }}">All publications →</a></p>
</section>
{% endfor %}

## research vision

{{ site.data.research.vision }}

Getting there requires three things at once: observation systems that see every city and settlement consistently; models whose outputs scientists and policymakers can interrogate rather than take on faith; and research questions set by what matters for people — health, safety, and fair access to a livable environment. Each project I take on is chosen to advance at least one of these fronts.
