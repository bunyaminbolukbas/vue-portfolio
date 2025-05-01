<script setup>
import profileImg from '@/assets/images/profilepic.png'
</script>

<template>
  <section id="about" class="py-20 px-4 bg-gray-50 dark:bg-zinc-900 transition-colors duration-300">
    <div class="max-w-3xl mx-auto flex flex-col items-center text-center">
      <!-- Foto -->
      <img
        :src="profileImg"
        alt="Photo of Bunyamin"
        class="w-40 h-40 md:w-48 md:h-48 rounded-full object-top object-cover mb-6 ring-2 ring-blue-500 dark:ring-blue-300 shadow-md"
      />

      <!-- Titel -->
      <h2 class="text-3xl font-bold mb-6 text-black dark:text-white">About me.</h2>

      <!-- Tekst netjes uitgelijnd -->
      <div class="text-left text-gray-600 dark:text-gray-300 text-lg leading-relaxed">
        <p>
          Hey there! I'm <span class="font-semibold">Bunyamin</span> — I specialize in frontend
          development with Vue, React, and TypeScript, but I’m also confident working with backend
          tools like Python, Flask, and Node.js.
        </p>

        <p>
          With a background in law and sales, I bring a unique mix of analytical thinking and
          communication skills to my work. I’m passionate about building modern, secure, and
          user-focused applications — especially when it comes to solving real-world problems.
        </p>

        <p>
          I'm currently open to new opportunities, so if you’re hiring or want to collaborate, shoot
          me a message!
        </p>
      </div>
    </div>
  </section>
</template>
