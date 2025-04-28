<script setup>
import profileImg from '@/assets/images/profilepic.png'
</script>

<template>
  <section id="about" class="py-20 px-4 bg-gray-50 dark:bg-zinc-900 transition-colors duration-300">
    <div class="max-w-3xl mx-auto text-center flex flex-col items-center">
      <!-- Foto -->
      <img
        :src="profileImg"
        alt="Photo of Bunyamin"
        class="w-50 h-50 rounded-full object-cover mb-9 ring-2 ring-blue-500 dark:ring-blue-300 shadow-md"
      />

      <!-- Titel & Tekst -->
      <h2 class="text-3xl font-bold mb-6 text-black dark:text-white">About Me</h2>
      <p class="text-gray-700 dark:text-gray-300 text-lg leading-relaxed">
        Hi, I'm <span class="font-semibold">Bunyamin</span> — a fullstack developer with a unique
        background in law, sales, and front-end development. I started my career at the Public
        Prosecutor’s Office, building a strong foundation in justice and security. Now I use that
        experience as a developer within the police, creating secure digital systems. I'm passionate
        about solving real-world problems through technology — with a focus on clean, responsive UI.
      </p>
    </div>
  </section>
</template>
