<script setup>
import { Github, Linkedin, Twitter, Mail } from 'lucide-vue-next'
</script>

<template>
  <section
    class="flex flex-col items-center justify-center text-center py-24 px-4 bg-white text-black dark:bg-black dark:text-white transition-colors duration-300"
  >
    <h1 class="text-4xl md:text-6xl font-bold mb-4">Full Stack Developer</h1>
    <p class="text-gray-600 dark:text-gray-300 text-lg md:text-xl max-w-xl">
      Building digital experiences with modern technologies. Focused on creating elegant solutions
      to complex problems.
    </p>

    <div class="flex space-x-4 mt-6">
      <a
        href="https://github.com/Bunyamin-1058754"
        target="_blank"
        class="border p-3 rounded hover:bg-gray-100 dark:hover:bg-gray-800 transition"
      >
        <Github class="w-5 h-5" />
      </a>
      <a
        href="https://www.linkedin.com/in/bunyaminbolukbas/"
        target="_blank"
        class="border p-3 rounded hover:bg-gray-100 dark:hover:bg-gray-800 transition"
      >
        <Linkedin class="w-5 h-5" />
      </a>
      <a
        href="https://twitter.com"
        target="_blank"
        class="border p-3 rounded hover:bg-gray-100 dark:hover:bg-gray-800 transition"
      >
        <Twitter class="w-5 h-5" />
      </a>
      <a
        href="mailto:hello@example.com"
        class="border p-3 rounded hover:bg-gray-100 dark:hover:bg-gray-800 transition"
      >
        <Mail class="w-5 h-5" />
      </a>
    </div>
  </section>
</template>
