<template>
  <section
    id="projects"
    class="py-24 px-4 bg-white text-black dark:bg-black dark:text-white transition-colors duration-300"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold mb-6">
          Featured <span class="text-gradient">Projects</span>
        </h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto rounded-full mb-6"></div>
        <p class="text-xl text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
          Here are some of my recent projects that showcase my skills and passion for creating innovative solutions.
        </p>
      </div>

      <!-- Projects Grid -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3 mb-16">
        <ProjectCard 
          v-for="(project, index) in projects" 
          :key="project.title" 
          v-bind="project"
          class="animate-fade-in-up"
          :style="{ animationDelay: `${index * 0.1}s` }"
        />
      </div>

      <!-- Call to Action -->
      <div class="text-center">
        <div class="inline-flex items-center gap-4 p-8 bg-gradient-to-r from-blue-50 to-purple-50 dark:from-blue-900/20 dark:to-purple-900/20 rounded-2xl border border-blue-200/50 dark:border-blue-700/50">
          <div class="flex-shrink-0">
            <div class="w-16 h-16 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center">
              <Rocket class="w-8 h-8 text-white" />
            </div>
          </div>
          <div class="text-left">
            <h3 class="text-xl font-bold mb-2">Have a project in mind?</h3>
            <p class="text-gray-600 dark:text-gray-300 mb-4">Let's work together to bring your ideas to life!</p>
            <a
              href="#contact"
              class="inline-flex items-center gap-2 btn-primary px-6 py-3 rounded-full text-white font-semibold transition-all duration-300"
            >
              Start a Project
              <ArrowRight class="w-4 h-4" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Rocket, ArrowRight } from 'lucide-vue-next'
import ProjectCard from './ProjectCard.vue'
import walletimg from '@/assets/images/n8n.png'
import iphoneimg from '@/assets/images/iphoneimg.png'
import craneimg from '@/assets/images/crane.png'

const projects = [
  {
    title: 'Fullstack Weather App',
    description:
      'A comprehensive weather dashboard built with React.js frontend and Python backend. Features real-time weather data, responsive design, and intuitive user interface with advanced API integration.',
    image: iphoneimg,
    link: 'https://github.com/bunyaminbolukbas/React-Weather-webapp',
    tags: ['React', 'Python', 'Flask', 'Vite', 'OpenAPI', 'SQLite3'],
  },
  {
    title: 'n8n Crypto Wallet',
    description:
      'An automated cryptocurrency wallet management system built with n8n workflows. Integrates blockchain APIs for real-time transaction monitoring, automated trading signals, and portfolio management.',
    image: walletimg,
    link: 'https://github.com/bunyaminbolukbas/n8n-Crypto-Wallet',
    tags: ['n8n', 'TypeScript', 'Automation', 'Webhooks', 'Crypto'],
  },
  {
    title: 'Crane Simulation Tool',
    description:
      'Advanced crane simulator developed in collaboration with Eye-Concept Industrial Automation B.V. Features realistic physics-based movement, MQTT communication, and industrial automation protocols.',
    image: craneimg,
    link: 'https://github.com/bunyaminbolukbas/Crane-Simulation-Tool',
    tags: ['Python', 'C#', 'MQTT', 'Unity', 'Simulation', 'IoT'],
  },
]
</script>