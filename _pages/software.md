---
layout: page
permalink: /software/
title: Software
description: Interactive animations, games, and open-source contributions
nav: true
nav_order: 6
---

<!-- _pages/software.md -->

<div class="software">

  <!-- Interactive Animations Section -->
  <div class="section-header">
    <h3>Interactive Animations</h3>
    <p class="text-muted">Physics simulations and interactive visualizations</p>
  </div>

  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mb-5">
    
    <!-- Example Animation Project -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-wave-square fa-3x"></i>
          </div>
          <h5 class="card-title">Physics Simulation</h5>
          <p class="card-text flex-grow-1">Interactive wave propagation and interference patterns visualization.</p>
          <div class="mt-auto">
            <a href="#" class="btn software-btn me-2">
              <i class="fas fa-play"></i> Demo
            </a>
            <a href="#" class="btn software-btn-outline">
              <i class="fab fa-github"></i> Code
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Add more animation projects here -->
    
  </div>

  <!-- Games Section -->
  <div class="section-header">
    <h3>Games</h3>
    <p class="text-muted">Interactive games and puzzles</p>
  </div>

  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mb-5">
    
    <!-- Example Game Project -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-gamepad fa-3x"></i>
          </div>
          <h5 class="card-title">Quantum Puzzle Game</h5>
          <p class="card-text flex-grow-1">Educational game exploring quantum mechanics principles through interactive puzzles.</p>
          <div class="mt-auto">
            <a href="#" class="btn software-btn me-2">
              <i class="fas fa-play"></i> Play
            </a>
            <a href="#" class="btn software-btn-outline">
              <i class="fab fa-github"></i> Code
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Add more game projects here -->
    
  </div>

  <!-- Open Source Contributions Section -->
  <div class="section-header">
    <h3>Open Source Contributions</h3>
    <p class="text-muted">GitHub repositories and community contributions</p>
  </div>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    
    <!-- Example Open Source Project -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">quantum-simulator</h5>
              <p class="text-muted small mb-0">Python • Quantum Computing</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> 42
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> 8
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">Open-source quantum circuit simulator with visualization capabilities for educational purposes.</p>
          <div class="mt-auto">
            <a href="#" class="btn software-btn me-2">
              <i class="fab fa-github"></i> Repository
            </a>
            <a href="#" class="btn software-btn-outline">
              <i class="fas fa-book"></i> Docs
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Add more open source projects here -->
    
  </div>

  <!-- Featured Software -->
  <div class="section-header">
    <h3>Featured Software</h3>
    <p class="text-muted">Highlighted projects and tools</p>
  </div>

  <div class="row mb-5">
    <div class="col-12">
      <div class="card software-featured">
        <div class="card-body">
          <div class="row align-items-center">
            <div class="col-md-2 text-center">
              <div class="software-icon-large">
                <i class="fas fa-microchip fa-4x"></i>
              </div>
            </div>
            <div class="col-md-7">
              <h4 class="card-title">Photonic Circuit Designer</h4>
              <p class="card-text">Advanced web-based tool for designing and simulating integrated photonic circuits with real-time performance analysis and optimization suggestions.</p>
              <div class="tech-stack">
                <span class="badge bg-primary me-1">JavaScript</span>
                <span class="badge bg-success me-1">WebGL</span>
                <span class="badge bg-info me-1">Three.js</span>
                <span class="badge bg-warning text-dark">Python Backend</span>
              </div>
            </div>
            <div class="col-md-3 text-end">
              <a href="#" class="btn software-btn-lg mb-2 d-block">
                <i class="fas fa-external-link-alt"></i> Launch App
              </a>
              <a href="#" class="btn software-btn-outline">
                <i class="fab fa-github"></i> Source Code
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</div>

<style>
  .software {
    margin-top: 2rem;
  }

  .section-header {
    margin-bottom: 2rem;
    text-align: center;
  }

  .section-header h3 {
    color: var(--global-text-color);
    margin-bottom: 0.5rem;
  }

  .software-card {
    border: 1px solid var(--global-divider-color);
    border-radius: 12px;
    transition: all 0.3s ease;
    background: var(--global-card-bg-color);
  }

  .software-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: var(--global-theme-color);
  }

  [data-theme='dark'] .software-card:hover {
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
  }

  .software-featured {
    border: 2px solid var(--global-theme-color);
    border-radius: 15px;
    background: var(--global-card-bg-color);
  }

  .software-icon {
    color: var(--global-theme-color);
  }

  .software-icon-large {
    color: var(--global-theme-color);
    opacity: 0.8;
  }

  .software-btn {
    background: var(--global-theme-color) !important;
    border-color: var(--global-theme-color) !important;
    color: var(--global-bg-color) !important;
    padding: 0.375rem 0.75rem;
    border-radius: 6px;
    text-decoration: none;
    transition: all 0.15s ease-in-out;
    font-size: 0.875rem;
  }

  .software-btn:hover {
    background: var(--global-hover-color) !important;
    border-color: var(--global-hover-color) !important;
    color: var(--global-bg-color) !important;
    text-decoration: none;
    transform: translateY(-1px);
  }

  .software-btn-lg {
    background: var(--global-theme-color) !important;
    border-color: var(--global-theme-color) !important;
    color: var(--global-bg-color) !important;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.15s ease-in-out;
  }

  .software-btn-lg:hover {
    background: var(--global-hover-color) !important;
    border-color: var(--global-hover-color) !important;
    color: var(--global-bg-color) !important;
    text-decoration: none;
    transform: translateY(-1px);
  }

  .software-btn-outline {
    color: var(--global-theme-color) !important;
    background-color: transparent !important;
    border: 1px solid var(--global-theme-color) !important;
    padding: 0.375rem 0.75rem;
    border-radius: 6px;
    text-decoration: none;
    transition: all 0.15s ease-in-out;
    font-size: 0.875rem;
  }

  .software-btn-outline:hover {
    color: var(--global-bg-color) !important;
    background-color: var(--global-theme-color) !important;
    border-color: var(--global-theme-color) !important;
    text-decoration: none;
    transform: translateY(-1px);
  }

  .github-stats .badge {
    font-size: 0.7rem;
  }

  .tech-stack {
    margin-top: 1rem;
  }

  .tech-stack .badge {
    font-size: 0.75rem;
    padding: 0.4em 0.6em;
  }

  @media (max-width: 768px) {
    .software-featured .col-md-3 {
      text-align: center !important;
      margin-top: 1rem;
    }

    .software-btn-lg {
      display: inline-block !important;
      margin-right: 0.5rem;
    }
  }
</style>