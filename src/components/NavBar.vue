<template>
  <header class="sticky top-0 z-50 w-full border-b bg-white/95 backdrop-blur">
    <div class="container mx-auto flex h-14 items-center justify-between px-4">
      <!-- Linkerzijde: Logo en navigatie -->
      <div class="flex items-center space-x-8">
        <div class="font-bold text-lg">Bunyamin.dev</div>
        <nav class="hidden md:flex space-x-6 text-sm font-medium">
          <a href="#about" class="hover:text-blue-600 transition">About</a>
          <a href="#projects" class="hover:text-blue-600 transition">Projects</a>
          <a href="#contact" class="hover:text-blue-600 transition">Contact</a>
        </nav>
      </div>

      <!-- Rechterzijde: Resume-knop -->
      <a
        href="/resume.pdf"
        class="border px-4 py-1.5 rounded-md text-sm hover:bg-gray-100 transition"
      >
        Resume
      </a>
    </div>
  </header>
</template>

<script setup>
// geen logica nodig
</script>

<style scoped>
/* optioneel extra styling */
</style>
