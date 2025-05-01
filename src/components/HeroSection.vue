<script setup>
import { Github, Linkedin, Mail } from 'lucide-vue-next'
</script>

<template>
  <section
    class="flex items-center justify-center py-32 px-4 bg-black text-white transition-colors duration-300 min-h-screen"
  >
    <div class="max-w-2xl text-left animate-fade-in-up">
      <h1 class="text-4xl md:text-6xl font-bold mb-6">Hi, I'm Bünyamin.</h1>
      <h2 class="text-2xl md:text-4xl font-bold mb-6">I'm a frontend web developer</h2>
      <p class="text-gray-300 text-lg md:text-xl mb-8">
        Not your average developer — I specialize in building modern, responsive web applications.
        With a background in law and sales, I bring a unique perspective to everything I build.
      </p>

      <div class="flex space-x-4">
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
    </div>
  </section>
</template>
