---
layout: page
permalink: /publications/
title: Publications
description:
nav: true
nav_order: 3
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature with Google Scholar Button -->
<div class="d-flex justify-content-between align-items-center mb-4">
  <div class="flex-grow-1 me-3">
    {% if site.bib_search %}
      <script src="{{ '/assets/js/bibsearch.js' | relative_url | bust_file_cache }}" type="module"></script>
      <input type="text" id="bibsearch" spellcheck="false" autocomplete="off" class="search bibsearch-form-input" placeholder="Type to filter">
    {% endif %}
  </div>
  <div>
    <a href="https://scholar.google.com/citations?user={{ site.scholar_userid }}" target="_blank" class="btn scholar-btn">
      <i class="ai ai-google-scholar"></i> View on Google Scholar
    </a>
  </div>
</div>

<div class="publications">

{% bibliography %}

</div>
