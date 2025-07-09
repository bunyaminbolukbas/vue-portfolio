<template>
  <section
    id="tech"
    class="py-24 px-4 bg-gray-50 dark:bg-zinc-900 transition-colors duration-300"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-black dark:text-white">
          Tech <span class="text-gradient">Stack</span>
        </h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto rounded-full mb-6"></div>
        <p class="text-xl text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
          Technologies and tools I use to bring ideas to life
        </p>
      </div>

      <!-- Tech Categories -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-4 mb-16">
        <div
          v-for="(tech, index) in technologies"
          :key="tech.category"
          class="group hover-lift rounded-2xl p-8 bg-white dark:bg-gray-900 shadow-lg border border-gray-200 dark:border-gray-700 animate-fade-in-up"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <!-- Icon -->
          <div class="mb-6">
            <div class="w-16 h-16 bg-gradient-to-r from-blue-600 to-purple-600 rounded-2xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300">
              <component :is="tech.icon" class="w-8 h-8 text-white" />
            </div>
          </div>

          <!-- Category Title -->
          <h3 class="text-xl font-bold mb-4 text-gray-900 dark:text-white group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors duration-200">
            {{ tech.category }}
          </h3>

          <!-- Skills -->
          <div class="space-y-3">
            <div 
              v-for="skill in tech.skills" 
              :key="skill"
              class="flex items-center gap-3 p-3 bg-gray-50 dark:bg-gray-800 rounded-lg hover:bg-blue-50 dark:hover:bg-blue-900/20 transition-colors duration-200 group/skill"
            >
              <div class="w-2 h-2 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full group-hover/skill:scale-125 transition-transform duration-200"></div>
              <span class="text-sm font-medium text-gray-700 dark:text-gray-300 group-hover/skill:text-blue-600 dark:group-hover/skill:text-blue-400 transition-colors duration-200">
                {{ skill }}
              </span>
            </div>
          </div>
        </div>
      </div>

      <!-- Experience Timeline -->
      <div class="bg-white dark:bg-gray-900 rounded-2xl p-8 shadow-lg border border-gray-200 dark:border-gray-700">
        <h3 class="text-2xl font-bold mb-8 text-center text-gray-900 dark:text-white">
          Professional Journey
        </h3>
        
        <div class="space-y-8">
          <div 
            v-for="(milestone, index) in milestones" 
            :key="index"
            class="flex items-start gap-6 animate-fade-in-left"
            :style="{ animationDelay: `${index * 0.2}s` }"
          >
            <div class="flex-shrink-0 w-12 h-12 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center">
              <span class="text-white font-bold text-sm">{{ milestone.year }}</span>
            </div>
            <div class="flex-1 pb-8 border-b border-gray-200 dark:border-gray-700 last:border-b-0">
              <h4 class="text-lg font-semibold text-gray-900 dark:text-white mb-2">
                {{ milestone.title }}
              </h4>
              <p class="text-gray-600 dark:text-gray-300">
                {{ milestone.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Code, Database, Cloud, Wrench } from 'lucide-vue-next'

const technologies = [
  {
    category: 'Frontend',
    icon: Code,
    skills: ['Vue.js', 'React', 'TypeScript', 'JavaScript', 'TailwindCSS', 'HTML5', 'CSS3'],
  },
  {
    category: 'Backend',
    icon: Database,
    skills: ['Python', 'Node.js', 'Flask', 'SQL', 'SQLite3', 'PostgreSQL', 'REST APIs'],
  },
  {
    category: 'DevOps',
    icon: Cloud,
    skills: ['Docker', 'Netlify', 'Linux', 'Kubernetes', 'Git', 'GitHub', 'CI/CD'],
  },
  {
    category: 'Tools',
    icon: Wrench,
    skills: ['Vite', 'AI Tools', 'Postman', 'Jest', 'Vercel', 'n8n', 'MQTT'],
  },
]

const milestones = [
  {
    year: '2022',
    title: 'Started Web Development Journey',
    description: 'Began learning modern web technologies, focusing on JavaScript and Vue.js'
  },
  {
    year: '2023',
    title: 'Full-Stack Development',
    description: 'Expanded skills to include backend development with Python and Flask'
  },
  {
    year: '2024',
    title: 'Professional Projects',
    description: 'Started working on complex projects including automation and industrial applications'
  },
  {
    year: '2025',
    title: 'Open for Opportunities',
    description: 'Currently seeking new challenges and collaboration opportunities'
  }
]
</script>