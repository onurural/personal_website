<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-wrapper">
    <div class="container">
      <header>
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/projects">Projects</RouterLink>
          <RouterLink to="/resume">Resume</RouterLink>
        </nav>
      </header>

      <main>
        <RouterView />
      </main>
    </div>
  </div>
</template>

<style>
:root {
  --primary-color: #333;
  --secondary-color: #666;
  --link-color: #0066cc;
  --background-color: #ffffff;
  --max-width: 1200px;
  --content-padding: 2rem;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell,
    'Open Sans', 'Helvetica Neue', sans-serif;
  line-height: 1.6;
  color: var(--primary-color);
  background-color: var(--background-color);
  min-height: 100vh;
}

.app-wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

.container {
  width: 100%;
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--content-padding);
  flex: 1;
  display: flex;
  flex-direction: column;
  position: relative;
}

header {
  position: fixed;
  top: 2rem;
  right: calc((100vw - 1600px) / 2);
  z-index: 100;
  padding: 1rem 0;
}

nav {
  display: flex;
  gap: 4rem;
  justify-content: flex-end;
}

nav a {
  color: #000000;
  text-decoration: none;
  font-size: 1.8rem;
  font-weight: 500;
  transition: color 0.2s;
}

nav a:hover,
nav a.router-link-active {
  color: #333333;
}

@media (max-width: 1400px) {
  header {
    right: calc((100vw - 1200px) / 2);
  }
}

@media (max-width: 768px) {
  header {
    position: static;
    width: 100%;
    padding: 1rem;
    margin-bottom: 2rem;
  }

  nav {
    justify-content: center;
    gap: 2rem;
  }

  nav a {
    font-size: 1.5rem;
  }
}

main {
  width: 100%;
  flex: 1;
  display: flex;
  flex-direction: column;
  padding-top: 1rem;
}

h1 {
  font-size: 2rem;
}

.container {
  width: 100%;
  margin: 0 auto;
  flex: 1;
  display: flex;
  flex-direction: column;
  position: relative;
}

main {
  width: 100%;
  flex: 1;
  display: flex;
  flex-direction: column;
}

/* Medium screens */
@media (max-width: 1024px) {
  :root {
    --content-padding: 2rem;
  }

  header {
    position: static;
    margin-bottom: 2rem;
  }

  nav {
    justify-content: flex-end;
    gap: 1.5rem;
  }
}

/* Small screens / tablets */
@media (max-width: 768px) {
  :root {
    --content-padding: 1.5rem;
  }

  nav {
    justify-content: center;
  }
}

/* Mobile screens */
@media (max-width: 480px) {
  :root {
    --content-padding: 1rem;
  }

  header {
    margin-bottom: 2rem;
    padding: 0.75rem 1rem;
  }

  nav {
    flex-direction: column;
    align-items: center;
    gap: 0.75rem;
  }

  nav a {
    text-align: center;
  }
}
</style>
