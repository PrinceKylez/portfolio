<script setup lang="ts">
import { ref } from 'vue'

const showLinks = ref(false)

const skills = ['C', 'C++', 'Java', 'Python', 'Django', 'SQL', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Git & GitHub', 'Basic Electronics']

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
  },
  {
    title: 'Java GUI Projects',
    description: 'Simple Java Swing projects made for programming and GUI activities.',
    tags: ['Java', 'Swing', 'GUI']
  },
  {
    title: 'Electronics Projects',
    description: 'Basic breadboard and circuit activities for Computer Engineering laboratory work.',
    tags: ['Electronics', 'Breadboard']
  }
]
</script>

<template>
  <div class="min-h-screen bg-slate-950 text-gray-200">
    <header class="border-b-4 border-slate-700 bg-slate-600 px-6 py-10 text-center">
      <h1 class="text-4xl font-bold text-white sm:text-5xl">Prince Kyle Quintos</h1>
      <h2 class="mt-2 text-2xl font-bold text-slate-950">BSCpE - 3A</h2>
      <p class="mt-2 text-sm text-slate-100">Computer Engineering Student • CSU Carig</p>
    </header>

    <main class="mx-auto grid max-w-5xl gap-6 px-5 py-8 md:grid-cols-2">
      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">About Me</h2>
        <p class="leading-7 text-slate-300">
          Just a random dude tryna code, survive college, and somehow make things work. 💻
        </p>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">Skills & Interests</h2>
        <p class="mb-4 leading-7 text-slate-300">Things I currently learn and work with as a Computer Engineering student.</p>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in skills"
            :key="skill"
            class="rounded-md border border-slate-600 bg-slate-700 px-3 py-2 text-xs text-slate-200"
          >
            {{ skill }}
          </span>
        </div>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg md:col-span-2">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">Resume</h2>
        <div class="grid gap-5 md:grid-cols-2">
          <div>
            <h3 class="text-lg font-bold text-white">Education</h3>
            <p class="mt-2 text-slate-300">Bachelor of Science in Computer Engineering</p>
            <p class="text-slate-400">CSU Carig • 3rd Year</p>
          </div>
          <div>
            <h3 class="text-lg font-bold text-white">What I Work With</h3>
            <p class="mt-2 text-slate-300">Programming, databases, web development, Git/GitHub, and basic electronics.</p>
          </div>
        </div>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg md:col-span-2">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">Recent Projects</h2>
        <div class="grid gap-4 md:grid-cols-3">
          <article
            v-for="project in projects.slice(0, 3)"
            :key="project.title"
            class="rounded-lg border border-slate-700 bg-slate-900 p-5 transition hover:-translate-y-1 hover:border-slate-500"
          >
            <h3 class="text-lg font-bold text-white">{{ project.title }}</h3>
            <p class="mt-3 text-sm leading-6 text-slate-400">{{ project.description }}</p>
            <div class="mt-4 flex flex-wrap gap-2">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="rounded-md bg-slate-700 px-2 py-1 text-xs text-slate-300"
              >
                {{ tag }}
              </span>
            </div>
          </article>
        </div>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">Experience</h2>
        <h3 class="text-lg font-bold text-white">OJT / Internship</h3>
        <p class="mt-2 text-slate-300">IT Department</p>
        <ul class="mt-3 list-disc space-y-2 pl-5 text-sm leading-6 text-slate-400">
          <li>Technical support for live selling activities</li>
          <li>Excel and client information updates</li>
          <li>Document scanning and printing</li>
          <li>Basic graphic design and product flyers</li>
        </ul>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg">
        <h2 class="mb-4 border-b-2 border-slate-600 pb-2 text-2xl font-bold text-white">Other Projects</h2>
        <div class="space-y-3">
          <div v-for="project in projects.slice(3)" :key="project.title" class="rounded-lg bg-slate-900 p-4">
            <h3 class="font-bold text-white">{{ project.title }}</h3>
            <p class="mt-1 text-sm text-slate-400">{{ project.description }}</p>
          </div>
        </div>
      </section>

      <section class="rounded-xl border-2 border-slate-700 bg-slate-800 p-6 shadow-lg md:col-span-2">
        <h2 class="mb-3 text-2xl font-bold text-white">Click Something 👀</h2>
        <p class="text-slate-300">There might be some things hidden here.</p>
        <button
          @click="showLinks = true"
          class="mt-5 rounded-lg border border-indigo-400 bg-slate-700 px-4 py-3 text-white transition hover:bg-indigo-500"
        >
          🔗 My Links
        </button>
      </section>
    </main>

    <footer class="border-t-2 border-slate-800 px-6 py-6 text-center text-xs text-slate-500">
      <p>© 2026 Prince Kyle Quintos</p>
      <p class="mt-1">Made with Vue 3, TypeScript & Tailwind CSS</p>
    </footer>

    <div
      v-if="showLinks"
      class="fixed inset-0 z-50 flex items-center justify-center bg-black/75 p-5"
      @click.self="showLinks = false"
    >
      <div class="relative w-full max-w-md rounded-xl border-2 border-indigo-400 bg-slate-800 p-7 shadow-2xl">
        <button
          class="absolute right-4 top-2 text-3xl text-slate-400 hover:text-white"
          @click="showLinks = false"
        >
          ×
        </button>
        <h2 class="mb-4 text-2xl font-bold text-white">🔗 My Links</h2>
        <ul class="space-y-3 text-slate-300">
          <li><a class="text-indigo-300 hover:text-white" href="https://github.com/PrinceKylez" target="_blank">GitHub — PrinceKylez</a></li>
          <li><a class="text-indigo-300 hover:text-white" href="mailto:kylequintos002@gmail.com">Email — kylequintos002@gmail.com</a></li>
          <li><a class="text-indigo-300 hover:text-white" href="https://github.com/PrinceKylez/portfolio" target="_blank">Portfolio Repository</a></li>
          <li><a class="text-indigo-300 hover:text-white" href="https://www.facebook.com/itzur.prxnc/" target="_blank">Facebook — itzur.prxnc</a></li>
          <li><a class="text-indigo-300 hover:text-white" href="https://www.instagram.com/lost.pryncc/" target="_blank">Instagram — lost.pryncc</a></li>
          <li><a class="text-indigo-300 hover:text-white" href="https://steamcommunity.com/id/HaiseKing/" target="_blank">Steam — HaiseKing</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>
