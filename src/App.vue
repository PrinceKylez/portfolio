<script setup lang="ts">
import { ref } from 'vue'

const menuOpen = ref(false)

const skills = ['Vue 3', 'TypeScript', 'Tailwind CSS', 'Java', 'Python', 'Django', 'SQL', 'Git & GitHub']

const projects = [
  {
    title: 'Alpha Centauri',
    description: 'A Django-based planet management system with accounts, roles, and PostgreSQL data.',
    tags: ['Django', 'Python', 'PostgreSQL']
  },
  {
    title: 'Grow A Sanction',
    description: 'A database-focused system designed to help organize and manage university sanction records.',
    tags: ['Database', 'SQL', 'System Design']
  },
  {
    title: 'Love Scam Awareness',
    description: 'A research project exploring digital literacy and awareness factors related to online love scams.',
    tags: ['Research', 'Digital Literacy', 'Philippines']
  }
]

const closeMenu = () => {
  menuOpen.value = false
}
</script>

<template>
  <div class="min-h-screen overflow-x-hidden text-zinc-100">
    <header class="fixed inset-x-0 top-0 z-50 border-b border-white/10 bg-black/70 backdrop-blur-xl">
      <nav class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
        <a href="#home" class="text-lg font-bold tracking-tight">PK<span class="text-violet-400">.</span></a>

        <button class="rounded-lg border border-white/10 px-3 py-2 text-sm md:hidden" @click="menuOpen = !menuOpen">
          Menu
        </button>

        <div class="hidden items-center gap-8 text-sm text-zinc-400 md:flex">
          <a href="#about" class="transition hover:text-white">About</a>
          <a href="#skills" class="transition hover:text-white">Skills</a>
          <a href="#projects" class="transition hover:text-white">Projects</a>
          <a href="#contact" class="rounded-full bg-white px-5 py-2 font-medium text-black transition hover:bg-violet-200">Contact</a>
        </div>
      </nav>

      <div v-if="menuOpen" class="border-t border-white/10 px-6 py-4 md:hidden">
        <div class="flex flex-col gap-4 text-zinc-300">
          <a href="#about" @click="closeMenu">About</a>
          <a href="#skills" @click="closeMenu">Skills</a>
          <a href="#projects" @click="closeMenu">Projects</a>
          <a href="#contact" @click="closeMenu">Contact</a>
        </div>
      </div>
    </header>

    <main>
      <section id="home" class="mx-auto flex min-h-screen max-w-6xl items-center px-6 pt-24">
        <div class="max-w-4xl">
          <p class="mb-5 text-sm font-medium uppercase tracking-[0.3em] text-violet-400">Computer Engineering Student</p>
          <h1 class="text-5xl font-black leading-[0.95] tracking-tight sm:text-7xl lg:text-8xl">
            Hi, I'm<br />
            <span class="bg-gradient-to-r from-white via-violet-200 to-violet-500 bg-clip-text text-transparent">Prince Kyle.</span>
          </h1>
          <p class="mt-8 max-w-2xl text-lg leading-8 text-zinc-400 sm:text-xl">
            I build clean, practical digital experiences while learning software development, databases, and modern web technologies.
          </p>
          <div class="mt-10 flex flex-wrap gap-4">
            <a href="#projects" class="rounded-full bg-white px-6 py-3 font-semibold text-black transition hover:scale-105">View my work</a>
            <a href="#contact" class="rounded-full border border-white/15 px-6 py-3 font-semibold text-white transition hover:border-violet-400 hover:text-violet-300">Let's connect</a>
          </div>
        </div>
      </section>

      <section id="about" class="border-y border-white/10 bg-white/[0.02]">
        <div class="mx-auto grid max-w-6xl gap-12 px-6 py-24 md:grid-cols-[0.8fr_1.2fr]">
          <div>
            <p class="text-sm uppercase tracking-[0.25em] text-violet-400">01 / About</p>
            <h2 class="mt-4 text-4xl font-bold tracking-tight">A student who likes building things.</h2>
          </div>
          <div class="space-y-5 text-lg leading-8 text-zinc-400">
            <p>I'm a Computer Engineering student interested in software development, databases, and user-friendly systems.</p>
            <p>I enjoy turning school projects and ideas into working applications and continuously improving my coding skills through hands-on practice.</p>
          </div>
        </div>
      </section>

      <section id="skills" class="mx-auto max-w-6xl px-6 py-24">
        <p class="text-sm uppercase tracking-[0.25em] text-violet-400">02 / Skills</p>
        <h2 class="mt-4 text-4xl font-bold tracking-tight">Tools I work with</h2>
        <div class="mt-10 grid grid-cols-2 gap-3 sm:grid-cols-4">
          <div v-for="skill in skills" :key="skill" class="rounded-2xl border border-white/10 bg-white/[0.03] p-5 text-center font-medium text-zinc-200 transition hover:-translate-y-1 hover:border-violet-400/50 hover:bg-violet-400/5">
            {{ skill }}
          </div>
        </div>
      </section>

      <section id="projects" class="border-y border-white/10 bg-white/[0.02]">
        <div class="mx-auto max-w-6xl px-6 py-24">
          <p class="text-sm uppercase tracking-[0.25em] text-violet-400">03 / Projects</p>
          <h2 class="mt-4 text-4xl font-bold tracking-tight">Selected work</h2>
          <div class="mt-10 grid gap-6 md:grid-cols-3">
            <article v-for="project in projects" :key="project.title" class="group rounded-3xl border border-white/10 bg-black/30 p-7 transition hover:-translate-y-2 hover:border-violet-400/40">
              <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-violet-500/10 text-violet-300">✦</div>
              <h3 class="mt-8 text-2xl font-bold">{{ project.title }}</h3>
              <p class="mt-4 min-h-24 leading-7 text-zinc-400">{{ project.description }}</p>
              <div class="mt-6 flex flex-wrap gap-2">
                <span v-for="tag in project.tags" :key="tag" class="rounded-full bg-white/5 px-3 py-1 text-xs text-zinc-400">{{ tag }}</span>
              </div>
            </article>
          </div>
        </div>
      </section>

      <section id="contact" class="mx-auto max-w-6xl px-6 py-28">
        <div class="rounded-[2rem] border border-white/10 bg-gradient-to-br from-violet-500/10 to-white/[0.02] p-8 text-center sm:p-16">
          <p class="text-sm uppercase tracking-[0.25em] text-violet-400">04 / Contact</p>
          <h2 class="mt-5 text-4xl font-bold tracking-tight sm:text-6xl">Let's build something.</h2>
          <p class="mx-auto mt-5 max-w-xl text-zinc-400">Have a project, school collaboration, or just want to connect? Feel free to reach out.</p>
          <a href="mailto:kylequintos002@gmail.com" class="mt-8 inline-flex rounded-full bg-white px-7 py-3 font-semibold text-black transition hover:scale-105">kylequintos002@gmail.com</a>
        </div>
      </section>
    </main>

    <footer class="border-t border-white/10 py-8">
      <div class="mx-auto flex max-w-6xl flex-col gap-3 px-6 text-sm text-zinc-500 sm:flex-row sm:items-center sm:justify-between">
        <p>© 2026 Prince Kyle Quintos</p>
        <p>Built with Vue 3, TypeScript & Tailwind CSS.</p>
      </div>
    </footer>
  </div>
</template>
