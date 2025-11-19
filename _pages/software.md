---
layout: page
permalink: /software/
title: Software
description: Interactive simulations, tools and open-source contributions
nav: true
nav_order: 5
---

<!-- _pages/software.md -->

<script>
// GitHub API functions for live stats
async function fetchGitHubStats(owner, repo) {
  try {
    const response = await fetch(`https://api.github.com/repos/${owner}/${repo}`);
    if (response.ok) {
      const data = await response.json();
      return {
        stars: data.stargazers_count,
        forks: data.forks_count
      };
    }
  } catch (error) {
    console.warn(`Failed to fetch stats for ${owner}/${repo}:`, error);
  }
  return null;
}

function formatNumber(num) {
  if (num >= 1000) {
    return (num / 1000).toFixed(1) + 'k';
  }
  return num.toString();
}

async function updateGitHubStats() {
  const repos = [
    { owner: 'tensorflow', repo: 'tensorflow', cardId: 'tensorflow-card' },
    { owner: 'pytorch', repo: 'pytorch', cardId: 'pytorch-card' },
    { owner: 'qiskit', repo: 'qiskit', cardId: 'qiskit-card' },
    { owner: 'PennyLaneAI', repo: 'pennylane', cardId: 'pennylane-card' },
    { owner: 'qutip', repo: 'qutip', cardId: 'qutip-card' }
  ];

  // Fetch all repo stats
  const statsPromises = repos.map(async (repo) => {
    const stats = await fetchGitHubStats(repo.owner, repo.repo);
    return { ...repo, stats };
  });

  const repoData = await Promise.all(statsPromises);
  
  // Sort by stars (descending)
  repoData.sort((a, b) => {
    const starsA = a.stats ? a.stats.stars : 0;
    const starsB = b.stats ? b.stats.stars : 0;
    return starsB - starsA;
  });

  // Update stats and reorder cards
  const container = document.querySelector('#opensource-container');
  if (container) {
    repoData.forEach((repo, index) => {
      const card = document.getElementById(repo.cardId);
      if (card && repo.stats) {
        // Update stats
        const starsBadge = card.querySelector('.stars-count');
        const forksBadge = card.querySelector('.forks-count');
        
        if (starsBadge) starsBadge.textContent = formatNumber(repo.stats.stars);
        if (forksBadge) forksBadge.textContent = formatNumber(repo.stats.forks);
        
        // Reorder card
        container.appendChild(card);
      }
    });
  }
}

// Update stats when page loads
document.addEventListener('DOMContentLoaded', updateGitHubStats);
</script>

<style>
.github-stats .badge .stars-count,
.github-stats .badge .forks-count {
  color: var(--global-bg-color);
  font-weight: normal;
}

/* Make badge backgrounds theme-aware */
.github-stats .badge {
  background-color: var(--global-text-color) !important;
  color: var(--global-bg-color) !important;
}

/* Improve spacing and alignment for open source cards */
#opensource-container .software-icon {
  margin-right: 1rem;
}

#opensource-container .github-stats {
  display: flex;
  gap: 0.5rem;
  align-items: center;
}

#opensource-container .github-stats .badge {
  display: inline-flex;
  align-items: center;
  gap: 0.25rem;
  white-space: nowrap;
}

#opensource-container .card-title {
  margin-bottom: 0.25rem;
}

#opensource-container .d-flex.align-items-start {
  margin-bottom: 1rem;
}

/* Improve vertical spacing between cards - apply to all sections */
.software .col {
  margin-bottom: 1.5rem;
}

.software .software-card {
  margin-bottom: 0;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.software .software-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

/* Better card internal spacing - apply to all sections */
.software .card-body {
  padding: 1.5rem;
}

.software .card-text {
  margin-bottom: 1rem;
  line-height: 1.5;
}

/* Consistent card title spacing */
.software .card-title {
  margin-bottom: 0.5rem;
}

/* Ensure consistent icon spacing for all sections */
.software .software-icon {
  margin-bottom: 1rem;
}
</style>

<div class="software">

  <!-- Simulations and Animations -->
  <div class="section-header">
    <h3>Simulations and Animations</h3>
    <p class="text-muted">Physics simulations and interactive animations</p>
  </div>  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    
    <!-- Wavefunction Simulation -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-atom fa-3x"></i>
          </div>
          <h5 class="card-title">Wavefunction Simulation</h5>
          <p class="card-text flex-grow-1">Interactive wavefunction simulation with real-time visualization of wave propagation and interference patterns.</p>
          <div class="mt-auto">
            <a href="/assets/html/wavefunctionsim.html" class="btn software-btn me-2">
              <i class="fas fa-play"></i> Launch
            </a>
            <a href="https://github.com/bvolkangurses/wavefunctionsim" class="btn software-btn-outline">
              <i class="fab fa-github"></i> Code
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Wigner Function Simulation -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-chart-area fa-3x"></i>
          </div>
          <h5 class="card-title">Wigner Function Simulation</h5>
          <p class="card-text flex-grow-1">Design your own quantum state in phase space using the Wigner quasiprobability distribution and see it time evolve.</p>
          <div class="mt-auto">
            <a href="https://github.com/bvolkangurses/wignersim" class="btn software-btn-outline">
              <i class="fab fa-github"></i> Code
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Add more animation projects here -->
    
  </div>

    <!-- Tools and Demos -->
  <div class="section-header">
    <h3>Tools and Demos</h3>
    <p class="text-muted">Interactive tools and demonstrations</p>
  </div>

  <div class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    
    <!-- Example Game Project -->
    <!--
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
    -->

    <!-- Neural Network Architect -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-brain fa-3x"></i>
          </div>
          <h5 class="card-title">Neural Network Architect</h5>
          <p class="card-text flex-grow-1">Interactive tool for designing and visualizing neural network architectures with drag-and-drop layer composition.</p>
          <div class="mt-auto">
            <a href="https://github.com/bvolkangurses/neuralnetarchitect" class="btn software-btn-outline">
              <i class="fab fa-github"></i> Code
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Photonic IC Designer -->
    <div class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="software-icon mb-3 text-center">
            <i class="fas fa-microchip fa-3x"></i>
          </div>
          <h5 class="card-title">Photonic IC Designer</h5>
          <p class="card-text flex-grow-1">Advanced web-based tool for designing and simulating integrated photonic circuits with real-time performance analysis.</p>
          <div class="tech-stack mb-3">
            <span class="badge bg-primary me-1">JavaScript</span>
            <span class="badge bg-success me-1">WebGL</span>
            <span class="badge bg-info me-1">Three.js</span>
            <span class="badge bg-warning text-dark">Python</span>
          </div>
          <div class="mt-auto">
            <a href="https://bvolkangurses.github.io/picdesigner/" class="btn software-btn me-2">
              <i class="fas fa-external-link-alt"></i> Launch
            </a>
            <a href="https://github.com/bvolkangurses/picdesigner" class="btn software-btn-outline">
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

  <div id="opensource-container" class="row row-cols-1 row-cols-md-2 g-4 mb-5">
    
    <!-- TensorFlow -->
    <div id="tensorflow-card" class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">tensorflow</h5>
              <p class="text-muted small mb-0">Python • Machine Learning</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> <span class="stars-count">185k</span>
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> <span class="forks-count">74k</span>
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">Open source platform for machine learning with comprehensive tools, libraries and community resources.</p>
          <div class="mt-auto">
            <a href="https://github.com/tensorflow/tensorflow" class="btn software-btn">
              <i class="fab fa-github"></i> Repository
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- PyTorch -->
    <div id="pytorch-card" class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">pytorch</h5>
              <p class="text-muted small mb-0">Python • Machine Learning</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> <span class="stars-count">82k</span>
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> <span class="forks-count">22k</span>
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">Open source machine learning framework that accelerates the path from research prototyping to production deployment.</p>
          <div class="mt-auto">
            <a href="https://github.com/pytorch/pytorch" class="btn software-btn">
              <i class="fab fa-github"></i> Repository
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Qiskit -->
    <div id="qiskit-card" class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">qiskit</h5>
              <p class="text-muted small mb-0">Python • Quantum Computing</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> <span class="stars-count">5.1k</span>
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> <span class="forks-count">2.3k</span>
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">Open-source SDK for working with quantum computers at the level of pulses, circuits and application modules.</p>
          <div class="mt-auto">
            <a href="https://github.com/qiskit/qiskit" class="btn software-btn">
              <i class="fab fa-github"></i> Repository
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- PennyLane -->
    <div id="pennylane-card" class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">pennylane</h5>
              <p class="text-muted small mb-0">Python • Quantum Computing</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> <span class="stars-count">2.3k</span>
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> <span class="forks-count">600+</span>
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">Cross-platform Python library for differentiable programming of quantum computers and quantum machine learning.</p>
          <div class="mt-auto">
            <a href="https://github.com/PennyLaneAI/pennylane" class="btn software-btn">
              <i class="fab fa-github"></i> Repository
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- QuTiP -->
    <div id="qutip-card" class="col">
      <div class="card software-card h-100">
        <div class="card-body d-flex flex-column">
          <div class="d-flex align-items-start mb-3">
            <div class="software-icon me-3">
              <i class="fab fa-github fa-2x"></i>
            </div>
            <div class="flex-grow-1">
              <h5 class="card-title mb-1">qutip</h5>
              <p class="text-muted small mb-0">Python • Quantum Computing</p>
            </div>
            <div class="github-stats">
              <span class="badge bg-secondary me-1">
                <i class="fas fa-star"></i> <span class="stars-count">1.9k</span>
              </span>
              <span class="badge bg-secondary">
                <i class="fas fa-code-branch"></i> <span class="forks-count">500+</span>
              </span>
            </div>
          </div>
          <p class="card-text flex-grow-1">QuTiP - Quantum Toolbox in Python. A library for the numerical simulation of open quantum systems.</p>
          <div class="mt-auto">
            <a href="https://github.com/qutip/qutip" class="btn software-btn">
              <i class="fab fa-github"></i> Repository
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Add more open source projects here -->
    
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