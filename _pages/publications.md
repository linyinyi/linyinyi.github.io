---
layout: page
permalink: /publications/
title: Publications
description: Peer-reviewed publications, maintained in BibTeX and grouped by year.
nav: true
nav_order: 2
---

Publications are listed in reverse chronological order and maintained in a single BibTeX file (<code>\_bibliography/papers.bib</code>). My name is <u>underlined</u> in author lists. The complete, citation-tracked record is on <a href="https://scholar.google.com/citations?user=5q5R47kAAAAJ&hl=en">Google Scholar</a>; citation counts are dynamic and may differ across databases.

<p class="yl-muted">
  Use the search box to filter — try a topic (<em>heat</em>, <em>resilience</em>, <em>SAR</em>), a co-author, a journal, or a year.
  Author PDFs are shared only where publisher policies permit; otherwise the DOI links to the version of record.
</p>

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
