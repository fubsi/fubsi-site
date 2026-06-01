<template>
  <section class="hero-section">
    <div class="tagline">
      <span class="decorative-line"></span> tech & infrastructure
    </div>
    
    <h1 class="massive-text hero-headline">
      <span class="hero-top-line">
        <span class="text-white">fubsi</span>
        <span class="smol-text">Frameworks & Unified Backends for Smart Integrations</span>
      </span>
      <span class="text-accent">builds things</span>
    </h1>
  </section>
</template>

<style scoped>
.hero-section {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2rem 1.5rem;
}

.tagline {
  display: flex;
  align-items: center;
  gap: 1rem;
  color: var(--text-white);
  font-size: 0.9rem;
  margin-bottom: 1.5rem;
  letter-spacing: 1px;
}

.hero-headline {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.1em;
}

.hero-top-line {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.1em;
}

@media (min-width: 768px) {
  .hero-section {
    padding-left: 10vw;
    padding-bottom: 10vh;
  }

  .hero-top-line {
    flex-direction: row;
    align-items: center;
    gap: 0.28em;
  }
}
</style>