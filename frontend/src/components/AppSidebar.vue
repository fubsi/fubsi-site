<script setup>
</script>

<template>
  <aside class="sidebar">
    <div class="logo">
      <span class="logo-mark">F_</span>
    </div>
    
    <div class="vertical-text-container">
      <span class="start-text">&larr; start</span>
    </div>

    <div class="socials">
      <a href="https://git.fubsi.win">gh</a>
      <a href="https://linkedin.fubsi.win">in</a>
      <!-- <a href="#">mail</a> -->
    </div>
  </aside>
</template>

<style scoped>
/* =========================================
   MOBILE FIRST (Standard für Smartphones) 
========================================= */
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 70px;
  width: 100%;
  background-color: var(--bg-sidebar);
  border-bottom: 1px solid var(--grid-line);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 0 1.5rem;
  z-index: 50;
  box-sizing: border-box;
}

.logo-mark {
  color: var(--accent);
  font-weight: 700;
  font-size: 1.5rem;
}

.vertical-text-container {
  display: none; /* Auf Mobile verstecken wir den riesigen Text */
}

.socials {
  display: flex;
  flex-direction: row;
  gap: 1.5rem;
}

.socials a {
  color: var(--text-muted);
  text-decoration: none;
  font-size: 1.1rem;
  transition: color 0.3s ease;
}

.socials a:hover {
  color: var(--accent-hover, var(--accent));
}

/* =========================================
   DESKTOP (Ab 768px) 
========================================= */
@media (min-width: 768px) {
  .sidebar {
    width: 100px;
    height: 100vh;
    bottom: 0;
    right: auto;
    border-bottom: none;
    border-right: 1px solid var(--grid-line);
    flex-direction: column;
    padding: 2rem 0;
  }

  .vertical-text-container {
    display: block;
    transform: rotate(-90deg);
    white-space: nowrap;
  }

  .start-text {
    font-size: 4rem;
    font-weight: 300;
    letter-spacing: 2px;
    color: transparent;
    -webkit-text-stroke: 1px var(--accent);
  }

  .socials {
    flex-direction: column;
  }

  .socials a {
    transform: rotate(-90deg);
    font-size: 0.9rem;
  }
}
</style>