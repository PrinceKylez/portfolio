<script setup lang="ts">
import { ref } from 'vue'

const showLinks = ref(false)

const skills = ['C', 'C++', 'Java', 'Python', 'Django', 'SQL', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Git & GitHub']

const projects = [
  {
    title: 'Alpha Centauri',
    description: 'A Django and PostgreSQL project for managing planets, accounts, and roles.',
    tags: ['Django', 'Python', 'PostgreSQL']
  },
  {
    title: 'Grow A Sanction',
    description: 'A database-focused system for organizing and managing university sanction records.',
    tags: ['Database', 'SQL', 'System']
  },
  {
    title: 'Love Scam Awareness',
    description: 'A research project about digital literacy and awareness of online love scams in the Philippines.',
    tags: ['Research', 'Awareness']
  }
]
</script>

<template>
  <div class="site">
    <header class="intro">
      <div class="name">Prince Kyle Quintos</div>
      <h1>BSCpE - 3A</h1>
      <p>Computer Engineering Student • CSU Carig</p>
    </header>

    <main class="contents">
      <section class="card">
        <h2>About Me</h2>
        <p>I am a Computer Engineering student from CSU Carig who enjoys learning programming and building useful systems.</p>
        <p>I am interested in software development, databases, web development, and electronics. Most of what I know comes from school projects and hands-on practice.</p>
      </section>

      <section class="card">
        <h2>Skills & Interests</h2>
        <p>These are some of the technologies and topics I currently work with.</p>
        <div class="skills">
          <span v-for="skill in skills" :key="skill">{{ skill }}</span>
        </div>
      </section>

      <section class="card projects-card">
        <h2>Projects</h2>
        <div class="projects">
          <article v-for="project in projects" :key="project.title" class="project">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="tags">
              <span v-for="tag in project.tags" :key="tag">{{ tag }}</span>
            </div>
          </article>
        </div>
      </section>

      <section class="card fun-card">
        <h2>Click Something 👀</h2>
        <p>There might be some things hidden here.</p>
        <div class="buttons">
          <button @click="showLinks = true">🔗 My Links</button>
        </div>
      </section>
    </main>

    <footer>
      <p>© 2026 Prince Kyle Quintos</p>
      <p>Made with Vue 3, TypeScript & Tailwind CSS</p>
    </footer>

    <div v-if="showLinks" class="overlay" @click.self="showLinks = false">
      <div class="popup">
        <button class="close" @click="showLinks = false">×</button>
        <h2>🔗 My Links</h2>
        <ul>
          <li><a href="https://github.com/PrinceKylez" target="_blank">GitHub — PrinceKylez</a></li>
          <li><a href="mailto:kylequintos002@gmail.com">Email — kylequintos002@gmail.com</a></li>
          <li><a href="https://github.com/PrinceKylez/portfolio" target="_blank">Portfolio Repository</a></li>
          <li><a href="https://www.facebook.com/itzur.prxnc/" target="_blank">Facebook — itzur.prxnc</a></li>
          <li><a href="https://www.instagram.com/lost.pryncc/" target="_blank">Instagram — lost.pryncc</a></li>
          <li><a href="https://steamcommunity.com/id/HaiseKing/" target="_blank">Steam — HaiseKing</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>
