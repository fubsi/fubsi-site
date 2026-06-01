<script setup>
import ProjectCard from '../components/ProjectCard.vue'
</script>

<template>
  <section class="page-section">
    <div class="section-header">
      <span class="decorative-line"></span>
      <h2>Meine Projekte</h2>
    </div>
    <ProjectCard
      title="fubsi-site"
      description="Mein digitales Zuhause: Eine minimalistische Vue.js Website als zentraler Hub für meine Projekte rund um Softwareentwicklung im Bereich KI, Webentwicklung und mehr."
      :techStack="['Vue.js', 'Docker', 'HTML', 'CSS']"
      repoUrl="https://git.fubsi.win/fubsi-site"
    />
    <ProjectCard
      title="ppt-mcp"
      description="Model Context Protocol server for creating, editing, and managing PowerPoint presentations with Python, using a provided template as the basis for new files."
      :techStack="['Python', 'MCP', 'AI', 'PowerPoint']"
      repoUrl="https://git.fubsi.win/ppt-mcp"
    />
  </section>
</template>

<style scoped>
.page-section {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  padding: 2rem 1.5rem;
}

@media (min-width: 768px) {
  .page-section {
    padding: 10vh 10vw 2rem;
    gap: 1.5rem;
  }
}
</style>