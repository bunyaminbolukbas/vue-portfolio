<template>
  <section
    id="tech"
    class="py-16 px-4 bg-white text-black dark:bg-black dark:text-white transition-colors duration-300"
  >
    <h2 class="text-3xl font-bold text-center mb-12">Tech Stack.</h2>

    <div class="grid gap-6 md:grid-cols-2">
      <div
        v-for="tech in technologies"
        :key="tech.category"
        class="rounded-xl border p-6 shadow-sm bg-white dark:bg-gray-900 dark:border-gray-700"
      >
        <h3 class="text-lg font-semibold mb-4">{{ tech.category }}</h3>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in tech.skills"
            :key="skill"
            class="inline-flex items-center rounded-md bg-blue-50 px-2 py-1 text-sm font-medium text-blue-700 ring-1 ring-inset ring-blue-200 dark:bg-blue-900 dark:text-blue-100 dark:ring-blue-800"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const technologies = [
  {
    category: 'Frontend',
    skills: ['Vue', 'TailwindCSS', 'React', 'TypeScript', 'JavaScript', 'HTML', 'CSS'],
  },
  {
    category: 'Backend',
    skills: ['Python', 'Node.js', 'Python', 'Flask', 'SQL', 'SQLite3', 'PostgreSQL'],
  },
  {
    category: 'DevOps',
    skills: ['Docker', 'Netlify', 'Linux', 'Kubernetes', 'Git', 'GitHub', 'CI/CD'],
  },
  {
    category: 'Tools',
    skills: ['Vite', 'AI', 'Postman', 'Jest', 'Vercel ', 'n8n', 'MQTT'],
  },
]
</script>
