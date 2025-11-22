---
layout: page
permalink: /simulations/quantumphasedarray/
title: Quantum Phased Array Visulation
description: Visualization of photon interference with quantum phased arrays
nav: false
---

<script>
  // Set session token to allow access to the simulation
  sessionStorage.setItem('auth_sim', 'true');
</script>

<div class="simulation-container">
  <iframe 
    src="/assets/html/quantumphasedarray.html" 
    style="width: 100%; height: 70vh; border: none; border-radius: 8px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); overflow: hidden;"
    sandbox="allow-scripts allow-same-origin allow-forms"
    scrolling="no"
  ></iframe>
</div>

<style>
body .container.mt-5 {
  margin-top: 1rem !important;
}

.post {
  padding-top: 0 !important;
  margin-top: 0 !important;
}

.post-header {
  margin-top: 0 !important;
  margin-bottom: 10px !important;
  padding-top: 0 !important;
}

.post-title {
  margin-top: 0 !important;
  margin-bottom: 5px !important;
}

.post-description {
  margin-bottom: 15px !important;
}

.simulation-container {
  margin-top: 0 !important;
  margin-bottom: 0 !important;
}
</style>
