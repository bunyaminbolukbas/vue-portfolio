<template>
  <section
    id="projects"
    class="py-16 px-4 bg-white text-black dark:bg-black dark:text-white transition-colors duration-300"
  >
    <h2 class="text-3xl font-bold text-center mb-12">Projects</h2>

    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
      <ProjectCard v-for="project in projects" :key="project.title" v-bind="project" />
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    title: 'E-commerce Platform',
    description:
      'A full-stack e-commerce platform built with Next.js, Prisma, and Stripe integration.',
    image: '/placeholder.svg',
    link: 'https://github.com',
    tags: ['Next.js', 'Prisma', 'Stripe'],
  },
  {
    title: 'Task Management App',
    description: 'A real-time task management application with team collaboration features.',
    image: '/placeholder.svg',
    link: 'https://github.com',
    tags: ['React', 'Node.js', 'Socket.io'],
  },
  {
    title: 'AI Chat Interface',
    description: 'An AI-powered chat interface with natural language processing capabilities.',
    image: '/placeholder.svg',
    link: 'https://github.com',
    tags: ['OpenAI', 'Next.js', 'TailwindCSS'],
  },
]
</script>
