<script setup lang="ts">
import { ref } from 'vue'
import { siFacebook, siGithub, siInstagram, siSteam } from 'simple-icons'

const showLinks = ref(false)
const scrollToTop = () => window.scrollTo({ top: 0, behavior: 'smooth' })

const skills = ['C', 'C++', 'Java', 'Python', 'Django', 'SQL', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Git & GitHub', 'Basic Electronics']

const projects = [
  { number: '01', title: 'Alpha Centauri', category: 'WEB APPLICATION', description: 'A Django and PostgreSQL project for managing planets, accounts, and roles.', tags: ['Django', 'Python', 'PostgreSQL'], icon: '✳', tone: 'violet' },
  { number: '02', title: 'Grow A Sanction', category: 'DATABASE SYSTEM', description: 'A database-focused system for organizing and managing university sanction records.', tags: ['Database', 'SQL', 'System'], icon: '↗', tone: 'lime' },
  { number: '03', title: 'Love Scam Awareness', category: 'RESEARCH PROJECT', description: 'A research project about digital literacy and awareness of online love scams in the Philippines.', tags: ['Research', 'Awareness'], icon: '♡', tone: 'peach' },
  { number: '04', title: 'Java GUI Projects', category: 'DESKTOP DEVELOPMENT', description: 'Simple Java Swing projects made for programming and GUI activities.', tags: ['Java', 'Swing', 'GUI'], icon: '▧', tone: 'blue' },
  { number: '05', title: 'Electronics Projects', category: 'COMPUTER ENGINEERING', description: 'Basic breadboard and circuit activities for Computer Engineering laboratory work.', tags: ['Electronics', 'Breadboard'], icon: '⌁', tone: 'pink' },
]
</script>

<template>
  <div class="site-shell min-h-screen antialiased">
    <header class="topbar">
      <a class="brand" href="#home" aria-label="Prince Kyle Quintos home"><span class="brand-mark">pk<span>.</span></span><span class="brand-caption">PORTFOLIO / 2026</span></a>
      <nav aria-label="Main navigation">
        <a href="#work">Work</a><a href="#about">About</a><a href="#experience">Experience</a>
      </nav>
      <button class="contact-pill" @click="showLinks = true"><span class="status-dot"></span> Let’s talk <span aria-hidden="true">↗</span></button>
    </header>

    <main id="home">
      <section class="hero page-width grid items-center gap-8 md:grid-cols-[1.1fr_.9fr]">
        <div class="hero-copy">
          <div class="eyebrow"><span class="eyebrow-line"></span> COMPUTER ENGINEERING · CSU CARIG</div>
          <h1>Hi, I’m<br /><span>Prince Kyle.</span></h1>
          <p class="hero-intro">I’m a fourth-year Computer Engineering student. I work on class projects, learn new tools, and try to make each project a little better than the last.</p>
          <div class="hero-actions"><a class="button button-primary" href="#work">Explore my work <span>↓</span></a><button class="text-link" @click="showLinks = true">Get in touch <span>↗</span></button></div>
        </div>
        <div class="hero-art">
          <div class="currently-card"><span class="project-category">A QUICK INTRO</span><h2>Right now</h2><div class="currently-row"><span>Studying</span><b>Computer Engineering</b></div><div class="currently-row"><span>Year</span><b>Fourth year</b></div><div class="currently-row"><span>Working with</span><b>Python · Django · SQL</b></div><div class="currently-row"><span>Also learning</span><b>Vue · TypeScript</b></div><p>Still learning as I go.</p></div>
        </div>
        <div class="hero-bottom"><span>SCROLL TO EXPLORE</span><span class="scroll-line"></span><span>01 / 04</span></div>
      </section>

      <section id="work" class="work-section section-pad">
        <div class="page-width">
          <div class="section-heading"><div><p class="eyebrow"><span class="eyebrow-line"></span> COURSEWORK & SIDE PROJECTS</p><h2>My <span>projects</span></h2></div><p class="section-aside">Class assignments, research,<br />and practice projects.</p></div>
          <div class="project-grid">
            <article v-for="project in projects" :key="project.number" class="project-card" :class="`tone-${project.tone}`">
              <div class="project-top"><span class="project-number">{{ project.number }} / 05</span><span class="project-icon">{{ project.icon }}</span></div>
              <div class="project-body"><p class="project-category">{{ project.category }}</p><h3>{{ project.title }}</h3><p class="project-description">{{ project.description }}</p><div class="tag-list"><span v-for="tag in project.tags" :key="tag">{{ tag }}</span></div></div>
              <div class="project-bottom"><span>PROJECT {{ project.number }}</span></div>
            </article>
          </div>
        </div>
      </section>

      <section id="about" class="about-section section-pad">
        <div class="page-width about-layout">
          <div class="about-title"><p class="eyebrow"><span class="eyebrow-line"></span> ABOUT</p><h2>A bit<br />about <span>me.</span></h2></div>
          <div class="about-content"><p class="about-lead">I’m studying Computer Engineering at CSU Carig.</p><p class="about-copy">Most of my experience so far comes from coursework and projects. I’ve worked with web apps, databases, Java GUI assignments, and basic electronics labs. I’m still building my skills and figuring out which parts I enjoy most.</p><div class="education-card"><span class="edu-icon">⌂</span><div><span class="project-category">EDUCATION</span><h3>B.S. Computer Engineering</h3><p>CSU Carig <span>·</span> Fourth year</p></div><span class="edu-date">2023 — NOW</span></div>
            <div class="skills-wrap"><p class="project-category">TOOLS & TOPICS I’M EXPLORING</p><div class="skill-list"><span v-for="skill in skills" :key="skill">{{ skill }}</span></div></div>
          </div>
        </div>
      </section>

      <section id="experience" class="experience-section section-pad"><div class="page-width experience-layout"><div><p class="eyebrow"><span class="eyebrow-line"></span> WORK EXPERIENCE</p><h2>Internship<span class="period">.</span></h2></div><div class="experience-card"><div class="experience-date">OJT</div><div><h3>IT Department</h3><p class="experience-sub">Tasks I helped with during my internship.</p><ul><li>Technical support for live selling activities</li><li>Excel and client information updates</li><li>Document scanning and printing</li><li>Basic graphic design and product flyers</li></ul></div></div></div></section>

      <section class="contact-section"><div class="page-width contact-inner"><p class="eyebrow"><span class="eyebrow-line"></span> CONTACT</p><h2>Want to get<br />in touch<span>?</span></h2><button class="button button-light" @click="showLinks = true">My links <span>↗</span></button></div></section>
    </main>

    <footer class="footer page-width"><a class="brand" href="#home"><span class="brand-mark">pk<span>.</span></span></a><span>© 2026 Prince Kyle Quintos</span><span>VUE 3 · TAILWIND CSS · TYPESCRIPT</span><button class="back-top" @click="scrollToTop">BACK TO TOP ↑</button></footer>

    <div v-if="showLinks" class="modal-backdrop" @click.self="showLinks = false" @keydown.esc="showLinks = false">
      <section class="links-modal" role="dialog" aria-modal="true" aria-labelledby="links-title">
        <button class="modal-close" aria-label="Close" @click="showLinks = false">×</button>
        <p class="eyebrow"><span class="eyebrow-line"></span> THE INTERNET IS A SMALL PLACE</p>
        <h2 id="links-title">Find me <span>around.</span></h2>
        <p class="modal-intro">Always happy to connect, talk projects, or swap ideas.</p>
        <a href="https://github.com/PrinceKylez" target="_blank" rel="noreferrer">
          <svg class="social-icon social-icon-fill" viewBox="0 0 24 24" aria-hidden="true"><path :d="siGithub.path" /></svg>
          GitHub <span>@PrinceKylez</span><b>↗</b>
        </a>
        <a href="mailto:kylequintos002@gmail.com">
          <svg class="social-icon" viewBox="0 0 24 24" aria-hidden="true"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m4 7 8 6 8-6"/></svg>
          Email <span>kylequintos002@gmail.com</span><b>↗</b>
        </a>
        <a href="https://www.facebook.com/itzur.prxnc/" target="_blank" rel="noreferrer">
          <svg class="social-icon social-icon-fill" viewBox="0 0 24 24" aria-hidden="true"><path :d="siFacebook.path" /></svg>
          Facebook <span>itzur.prxnc</span><b>↗</b>
        </a>
        <a href="https://www.instagram.com/lost.pryncc/" target="_blank" rel="noreferrer">
          <svg class="social-icon social-icon-fill" viewBox="0 0 24 24" aria-hidden="true"><path :d="siInstagram.path" /></svg>
          Instagram <span>lost.pryncc</span><b>↗</b>
        </a>
        <a href="https://steamcommunity.com/id/HaiseKing/" target="_blank" rel="noreferrer">
          <svg class="social-icon social-icon-fill" viewBox="0 0 24 24" aria-hidden="true"><path :d="siSteam.path" /></svg>
          Steam <span>HaiseKing</span><b>↗</b>
        </a>
      </section>
    </div>
  </div>
</template>
