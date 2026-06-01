<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  techStack: {
    type: Array,
    default: () => [],
  },
  repoUrl: {
    type: String,
    required: true,
  },
  repoLabel: {
    type: String,
    default: 'Zum Repo',
  },
})
</script>

<template>
  <article class="project-card">
    <div class="project-content">
      <h3 class="project-title">{{ title }}</h3>

      <ul v-if="techStack.length" class="badge-list" aria-label="Tech Stack">
        <li
          v-for="tech in techStack"
          :key="tech"
          class="badge"
        >
          {{ tech }}
        </li>
      </ul>

      <p class="project-description">{{ description }}</p>
    </div>

    <a
      class="repo-button"
      :href="repoUrl"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="Projekt-Repository in neuem Tab oeffnen"
    >
      {{ repoLabel }}
    </a>
  </article>
</template>

<style scoped>
.project-card {
  display: flex;
  flex-direction: column;
  width: min(100%, 1120px);
  box-sizing: border-box;
  gap: 1.2rem;
  padding: 1.25rem;
  border: 1px solid var(--grid-line);
  background-color: var(--bg-sidebar);
}

.project-content {
  display: flex;
  flex-direction: column;
  gap: 0.85rem;
}

.project-title {
  margin: 0;
  color: var(--text-main);
  font-size: 1.25rem;
  letter-spacing: 0.02em;
}

.project-description {
  margin: 0;
  color: var(--text-muted);
  line-height: 1.6;
  width: 66.6667%;
}

.repo-button {
  align-self: flex-start;
  text-decoration: none;
  background-color: var(--accent);
  color: var(--bg-main);
  border: 1px solid var(--accent);
  font-weight: 700;
  font-size: 0.92rem;
  padding: 0.7rem 1.1rem;
  transition: background-color 0.25s ease, color 0.25s ease;
}

.repo-button:hover {
  background-color: transparent;
  color: var(--accent);
}

@media (min-width: 768px) {
  .project-card {
    flex-direction: row;
    align-items: flex-start;
    justify-content: space-between;
    width: min(94%, 1120px);
    gap: 1.5rem;
    padding: 1.5rem;
  }

  .project-content {
    flex: 1;
    min-width: 0;
  }

  .repo-button {
    align-self: center;
    white-space: nowrap;
    margin-right: clamp(0.75rem, 2.5vw, 3rem);
  }
}
</style>
