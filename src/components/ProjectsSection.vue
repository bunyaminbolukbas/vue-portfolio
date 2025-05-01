<template>
  <section
    id="projects"
    class="py-16 px-4 bg-white text-black dark:bg-black dark:text-white transition-colors duration-300"
  >
    <h2 class="text-3xl font-bold text-center mb-12">Projects.</h2>

    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
      <ProjectCard v-for="project in projects" :key="project.title" v-bind="project" />
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'
import walletimg from '@/assets/images/n8n.png'
import iphoneimg from '@/assets/images/iphoneimg.png'
import craneimg from '@/assets/images/crane.png'
const projects = [
  {
    title: 'Fullstack Weather App',
    description:
      'A weather dashboard built with React.js frontend and a Python backend. Demonstrates fullstack API integration, responsiveness and user-friendly UI.',
    image: iphoneimg,
    link: 'https://github.com/Bunyamin-1058754/React-Weather-webapp',
    tags: ['React', 'Python', 'Flask', 'Vite', 'OpenAPI', 'SQLite3'],
  },
  {
    title: 'n8n Crypto Wallet',
    description:
      'An automated crypto wallet manager built using n8n, integrating blockchain API workflows for transaction monitoring and control.',
    image: walletimg,
    link: 'https://github.com/Bunyamin-1058754/n8n-Crypto-Wallet',
    tags: ['n8n', 'Typescript', 'Automation', 'Webhooks'],
  },
  {
    title: 'Crane Simulation',
    description:
      'A Python-based crane simulator developed in collaboration with Eye-Concept Industrial Automation B.V. to demonstrate mechanical and physics-based movement logic.',
    image: craneimg,
    link: 'https://github.com/Bunyamin-1058754/Crane-Simulation-Tool', //
    tags: ['Python', 'C#', 'MQTT', 'Unity', 'Simulation'],
  },
]
</script>
