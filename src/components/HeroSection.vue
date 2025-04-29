<script setup>
import { Github, Linkedin, Mail } from 'lucide-vue-next'
</script>

<template>
  <section
    class="flex flex-col items-center justify-center text-center py-32 px-4 bg-black text-white transition-colors duration-300 min-h-screen"
  >
    <h1 class="text-4xl md:text-6xl font-bold mb-6 animate-fade-in-up">Full Stack Developer</h1>
    <p class="text-gray-300 text-lg md:text-xl max-w-xl animate-fade-in-up delay-150">
      Building digital experiences with modern technologies. Focused on creating elegant solutions
      to complex problems.
    </p>

    <div class="flex space-x-4 mt-8 animate-fade-in-up delay-300">
      <a
        href="https://github.com/Bunyamin-1058754"
        target="_blank"
        class="border border-white p-3 rounded-full hover:bg-white hover:text-black transition"
      >
        <Github class="w-6 h-6" />
      </a>
      <a
        href="https://www.linkedin.com/in/bunyaminbolukbas/"
        target="_blank"
        class="border border-white p-3 rounded-full hover:bg-white hover:text-black transition"
      >
        <Linkedin class="w-6 h-6" />
      </a>

      <a
        href="mailto:bbe-operations@outlook.com"
        class="border border-white p-3 rounded-full hover:bg-white hover:text-black transition"
      >
        <Mail class="w-6 h-6" />
      </a>
    </div>
  </section>
</template>
