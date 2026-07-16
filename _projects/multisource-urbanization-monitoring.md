---
layout: page
title: Multisource urbanization monitoring
description: "Published · Long-term urban land-cover and expansion mapping from optical and SAR time series with machine learning."
img: assets/img/projects/project-urbanization.svg
importance: 5
related_publications: true
---

<p><span class="yl-status yl-status-published">Published</span></p>

**Research question.** How can optical and synthetic-aperture-radar observations be combined to map urban land cover and expansion reliably — through clouds, shadows, and seasons — over decades?

**Scale.** Large-scale and multi-city analyses, from intra-year urban renewal to multi-decadal expansion.

**Data.** Optical (Landsat, Sentinel-2, WorldView), SAR (Sentinel-1, TerraSAR-X, PALSAR), and LiDAR observations.

**Methods.** Deep learning and machine learning for data fusion — including sparse representation, stacked autoencoders, U-Net variants, and fuzzy-set approaches — applied to impervious-surface mapping, road extraction, and urban change detection.

**Key contributions.** This line of work established multisource fusion approaches that map annual impervious-surface dynamics at large scale {% cite lin2020incorporating %}, extract road networks from combined optical–SAR data {% cite lin2021leveraging %}, improve urban mapping under cloud and shadow contamination {% cite lin2019improving %}, and detect intra-year urban renewal in metropolitan cities {% cite lin2022intrayear %}. The resulting long-term urbanization records support analyses of environmental consequences, from heat exposure to coastal ecosystem change.

<div class="yl-media-placeholder">
  <img src="{{ '/assets/img/projects/project-urbanization.svg' | relative_url }}" alt="Stylized urban expansion motif with city blocks and radar scan lines" loading="lazy">
  <p class="yl-muted yl-caption">Illustrative motif — replace with a figure from the study (assets/img/projects/).</p>
</div>
