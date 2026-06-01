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
      <a href="https://git.fubsi.win" aria-label="GitHub" title="GitHub">
        <svg class="social-icon" viewBox="0 0 24 24" aria-hidden="true" focusable="false">
          <path
            fill="currentColor"
            d="M12 .5A12 12 0 0 0 8.2 23.9c.6.1.8-.3.8-.6v-2.2c-3.3.7-4-1.4-4-1.4-.5-1.3-1.2-1.6-1.2-1.6-1-.7.1-.7.1-.7 1.1.1 1.7 1.1 1.7 1.1 1 .1.6 2.5 3.5 2.3.1-.8.4-1.3.7-1.6-2.7-.3-5.5-1.3-5.5-6A4.7 4.7 0 0 1 5.5 9c-.1-.3-.5-1.5.1-3 0 0 1-.3 3.2 1.2a11.2 11.2 0 0 1 6 0C17 5.8 18 6 18 6c.6 1.5.2 2.7.1 3a4.7 4.7 0 0 1 1.2 3.3c0 4.7-2.8 5.7-5.5 6 .4.3.8 1 .8 2v2.9c0 .3.2.7.8.6A12 12 0 0 0 12 .5Z"
          />
        </svg>
      </a>
      <a href="https://discord.fubsi.win" aria-label="Discord" title="Discord">
        <svg class="social-icon" viewBox="0 0 24 24" aria-hidden="true" focusable="false">
          <path
            fill="currentColor"
            d="M20.3 4.4A16.6 16.6 0 0 0 16.2 3l-.2.4c1.8.5 2.7 1.2 3.5 1.9a13.1 13.1 0 0 0-4.2-2 14.8 14.8 0 0 0-6.6 0 13.1 13.1 0 0 0-4.2 2c.8-.7 1.7-1.4 3.5-1.9L7.8 3A16.6 16.6 0 0 0 3.7 4.4C1.1 8.3.4 12 .8 15.6a16.8 16.8 0 0 0 5 2.5l1.1-1.8a10.8 10.8 0 0 1-1.7-.8l.4-.3a11.8 11.8 0 0 0 10.8 0l.4.3c-.5.3-1 .6-1.7.8l1.1 1.8a16.8 16.8 0 0 0 5-2.5c.5-4.2-.8-7.8-2.8-11.2ZM8.7 13.3c-1 0-1.8-.9-1.8-2s.8-2 1.8-2c1 0 1.8.9 1.8 2s-.8 2-1.8 2Zm6.6 0c-1 0-1.8-.9-1.8-2s.8-2 1.8-2c1 0 1.8.9 1.8 2s-.8 2-1.8 2Z"
          />
        </svg>
      </a>
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
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: color 0.3s ease;
}

.social-icon {
  width: 1.2rem;
  height: 1.2rem;
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
    transform: none;
  }

  .social-icon {
    width: 1.1rem;
    height: 1.1rem;
  }
}
</style>