<template>
  <section class="hero-section">
    <div class="tagline">
      <span class="decorative-line"></span> tech & infrastructure
    </div>
    
    <h1 class="massive-text">
      <span class="white-text">fubsi</span><br>
      <span class="accent-text">builds things</span>
    </h1>
  </section>
</template>

<style scoped>
/* Hierhin kommt NUR das CSS, das spezifisch für die Hero-Section war (aus der alten App.vue) */
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

.decorative-line {
  display: inline-block;
  width: 30px;
  height: 2px;
  background-color: var(--accent);
}

.massive-text {
  margin: 0;
  line-height: 1.1;
  font-size: clamp(3rem, 16vw, 10rem);
  font-weight: 700;
  letter-spacing: -1px;
  word-break: break-word;
}

.white-text { color: var(--text-white); }
.accent-text { color: var(--accent); }

@media (min-width: 768px) {
  .hero-section {
    padding-left: 10vw;
    padding-bottom: 10vh;
  }
  .decorative-line { width: 50px; }
  .massive-text {
    letter-spacing: -2px;
    word-break: normal;
  }
}
</style>