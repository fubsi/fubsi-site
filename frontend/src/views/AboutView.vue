<script setup>
import '../assets/about.css'

const profile = {
  name: 'fubsi',
  headline: 'Computer Science Student',
  followers: 3,
  following: 3,
  repositories: 9,
  contributions: 250,
  githubUrl: 'https://github.com/fubsi',
  discordUrl: 'https://discordapp.com/users/170944308067696640'
}

const aboutPoints = [
  'Studiert aktuell die Welt der Artificial Intelligence und erkundet moderne Technologien.',
  'Fokus auf AI/ML, Webentwicklung und Software Engineering.',
  'Lernt kontinuierlich und baut innovative Projekte.',
  'Interesse an Machine Learning, Web-Apps und Open-Source-Entwicklung.'
]

const techStack = [
  'Python',
  'Java',
  'JavaScript',
  'HTML5',
  'CSS3',
  'LaTeX',
  'Streamlit',
  'Flask',
  'PyTorch',
  'Keras',
  'NumPy',
  'Pandas',
  'Matplotlib',
  'Git',
  'GitHub',
  'SQLite',
  'Postman',
  'Docker'
]

const featuredProjects = [
  {
    title: 'ppt-mcp',
    summary: 'PowerPoint-Automation mit MCP und Python fur template-basierte Workflows.',
    url: 'https://git.fubsi.win/ppt-mcp'
  },
  {
    title: 'mobsys-crm-ai',
    summary: 'AI-Komponente fur CRM-Workflows mit praxisnaher Python-Integration.',
    url: 'https://git.fubsi.win/mobsys-crm-ai'
  },
  {
    title: 'mobsys-backend-api',
    summary: 'Python-Backend-API fur den Zugriff auf eine Cloud-Datenbank.',
    url: 'https://git.fubsi.win/mobsys-backend-api'
  },
  {
    title: 'hackpy_library',
    summary: 'Lernorientiertes Python-Toolkit fur Ethical-Hacking-Ubungen und Labs.',
    url: 'https://git.fubsi.win/hackpy_library'
  }
]
</script>

<template>
  <section class="page-section about-page">
    <header class="about-hero">
      <div class="tagline">
        <span class="decorative-line"></span> about me
      </div>

      <h1 class="hero-title">
        <span class="text-white">Hi, ich bin {{ profile.name }}</span>
        <span class="text-accent">ich baue Software mit KI-Fokus</span>
      </h1>

      <p class="hero-copy">
        {{ profile.headline }} mit Leidenschaft fur AI/ML, Webentwicklung und robuste Backends.
        Auf GitHub teile ich Projekte rund um praktische Automation, APIs und experimentelle DevOps-Workflows.
      </p>
    </header>

    <section class="stats-grid" aria-label="GitHub Kennzahlen">
      <article class="stat-card">
        <span class="stat-label">Follower</span>
        <strong>{{ profile.followers }}</strong>
      </article>
      <article class="stat-card">
        <span class="stat-label">Following</span>
        <strong>{{ profile.following }}</strong>
      </article>
      <article class="stat-card">
        <span class="stat-label">Repos</span>
        <strong>{{ profile.repositories }}</strong>
      </article>
      <article class="stat-card">
        <span class="stat-label">Contributions/Jahr</span>
        <strong>{{ profile.contributions }}</strong>
      </article>
    </section>

    <section class="about-grid">
      <article class="panel">
        <div class="section-header">
          <span class="decorative-line"></span>
          <h2>Woran ich arbeite</h2>
        </div>
        <ul class="point-list">
          <li v-for="point in aboutPoints" :key="point">{{ point }}</li>
        </ul>
      </article>

      <article class="panel">
        <div class="section-header">
          <span class="decorative-line"></span>
          <h2>Kontakte</h2>
        </div>
        <div class="link-list">
          <a :href="profile.githubUrl" target="_blank" rel="noopener noreferrer">GitHub Profil</a>
          <a :href="profile.discordUrl" target="_blank" rel="noopener noreferrer">Discord</a>
        </div>
      </article>
    </section>

    <section class="panel">
      <div class="section-header">
        <span class="decorative-line"></span>
        <h2>Tech Stack</h2>
      </div>
      <ul class="badge-list tech-badges">
        <li v-for="tech in techStack" :key="tech" class="badge">{{ tech }}</li>
      </ul>
    </section>

    <section class="panel">
      <div class="section-header">
        <span class="decorative-line"></span>
        <h2>Featured Projects</h2>
      </div>
      <div class="project-list">
        <article v-for="project in featuredProjects" :key="project.title" class="project-item">
          <h3>{{ project.title }}</h3>
          <p>{{ project.summary }}</p>
          <a :href="project.url" target="_blank" rel="noopener noreferrer">Repository ansehen</a>
        </article>
      </div>
    </section>
  </section>
</template>
