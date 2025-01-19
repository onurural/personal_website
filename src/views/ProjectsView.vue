<script setup lang="ts">
interface Project {
  title: string
  description: string
  technologies: string[]
  link?: string
  github?: string
  image?: string
}

const projects: Project[] = [
  {
    title: 'Real-time Air Quality Prediction',
    description:
      'Developed a machine learning system for real-time air quality prediction using sensor data and environmental factors. Implemented data pipelines and predictive models to provide accurate forecasts.',
    technologies: ['Python', 'TensorFlow', 'Docker', 'AWS'],
    github: 'https://github.com/onurural/AirStream',
  },
  {
    title: 'Personal Website',
    description:
      'A clean, minimalist personal website built with Vue.js to showcase my projects and professional experience. Features responsive design and modern UI principles.',
    technologies: ['Vue.js', 'TypeScript', 'CSS3'],
    github: 'https://github.com/onurural/personal_website',
  },
  {
    title: 'Data Pipeline Automation',
    description:
      'Built scalable data pipelines for processing and analyzing large datasets. Implemented automated workflows and monitoring systems for data quality assurance.',
    technologies: ['Python', 'Apache Airflow', 'PostgreSQL', 'Docker'],
    github: 'https://github.com/yourusername/data-pipeline-automation',
  },
]
</script>

<template>
  <div class="projects">
    <h1>Projects</h1>
    <div class="projects-grid">
      <div v-for="project in projects" :key="project.title" class="project-card">
        <div class="project-content">
          <h2>{{ project.title }}</h2>
          <p class="description">{{ project.description }}</p>
          <div class="technologies">
            <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
              {{ tech }}
            </span>
          </div>
          <div class="links">
            <a
              v-if="project.github"
              :href="project.github"
              target="_blank"
              rel="noopener"
              class="link-button"
            >
              View on GitHub
            </a>
            <a
              v-if="project.link"
              :href="project.link"
              target="_blank"
              rel="noopener"
              class="link-button"
            >
              Live Demo
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.projects {
  width: 100vw;
  min-height: 100vh;
  margin: 0;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
}

h1 {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 2rem;
  color: var(--primary-color);
}

.projects-grid {
  width: 100%;
  max-width: 1800px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  padding: 2rem;
}

.project-card {
  width: 100%;
  background-color: #fff;
  border: 1px solid #eee;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
  padding: 1.5rem;
  display: flex;
}

.project-card:hover {
  transform: translateY(-4px);
}

.project-content {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  width: 100%;
}

h2 {
  font-size: 2rem;
  color: var(--primary-color);
  margin: 0;
}

.description {
  font-size: 1.1rem;
  color: var(--secondary-color);
  line-height: 1.4;
  margin: 0;
}

.technologies {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin: 0;
}

.tech-tag {
  background-color: #f0f0f0;
  color: var(--secondary-color);
  padding: 0.5rem 1rem;
  border-radius: 16px;
  font-size: 0.9rem;
}

.links {
  display: flex;
  gap: 1rem;
  margin: 0;
}

.link-button {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background-color: var(--link-color);
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-size: 1rem;
  transition: background-color 0.2s;
}

.link-button:hover {
  background-color: #0052a3;
}

@media (max-width: 768px) {
  .projects {
    padding: 1rem;
  }

  .projects-grid {
    padding: 1rem;
    gap: 1.5rem;
  }

  .project-card {
    aspect-ratio: auto;
    min-height: 300px;
    padding: 1.5rem;
  }

  h1 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
  }

  h2 {
    font-size: 1.5rem;
  }

  .description {
    font-size: 1rem;
  }
}
</style>
