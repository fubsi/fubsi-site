<script setup>
</script>

<template>
  <nav class="top-nav">
    <div class="nav-links">
        <router-link to="/">Start</router-link>
        <router-link to="/projects">Projekte</router-link>
        <router-link to="/about">Über mich</router-link>
    </div>
    <!--<button class="cta-button">kontakt aufnehmen &rarr;</button>-->
  </nav>
</template>

<style scoped>
/* Aktive Seite hervorheben */
.nav-links a.router-link-active {
  color: var(--accent);
  font-weight: 700;
}

/* =========================================
   MOBILE FIRST
========================================= */
.top-nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem 1.5rem;
  gap: 2rem;
}

.nav-links {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  text-align: center;
  width: 100%;
}

.nav-links a {
  color: var(--text-muted);
  text-decoration: none;
  font-size: 1.1rem;
  letter-spacing: 1px;
  transition: color 0.3s ease;
}

.nav-links a:hover {
  color: var(--accent-hover, var(--accent));
}

.cta-button {
  background-color: var(--accent);
  color: var(--bg-main);
  border: none;
  padding: 1rem 2rem;
  font-family: inherit;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  width: 100%;
  transition: background-color 0.3s ease;
}

.cta-button:hover {
  background-color: var(--accent-hover, #f0ae88);
}

/* =========================================
   DESKTOP
========================================= */
@media (min-width: 768px) {
  .top-nav {
    flex-direction: row;
    justify-content: space-between;
    padding: 2rem 4rem;
  }

  .nav-links {
    flex-direction: row;
    gap: 4rem;
    flex-grow: 1;
    justify-content: center;
  }
  
  .nav-links a { font-size: 0.9rem; }
  .cta-button { width: auto; }
}
</style>