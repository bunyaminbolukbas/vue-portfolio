<template>
  <header
    class="sticky top-0 z-50 w-full border-b bg-white/95 text-black dark:bg-black/90 dark:text-white transition-colors backdrop-blur"
  >
    <div class="container mx-auto flex h-14 items-center justify-between px-4">
      <!-- Linkerkant -->
      <div class="flex items-center space-x-8">
        <div class="font-bold text-lg">Bunyamin.dev</div>
        <nav class="hidden md:flex space-x-6 text-sm font-medium">
          <a href="#about" class="hover:text-blue-600 dark:hover:text-blue-400 transition">About</a>
          <a href="#projects" class="hover:text-blue-600 dark:hover:text-blue-400 transition"
            >Projects</a
          >
          <a href="#contact" class="hover:text-blue-600 dark:hover:text-blue-400 transition"
            >Contact</a
          >
        </nav>
      </div>

      <!-- Rechterkant -->
      <div class="flex items-center space-x-2">
        <ThemeToggle />
        <a
          href="/resume.pdf"
          class="border px-4 py-1.5 rounded-md text-sm hover:bg-gray-100 dark:hover:bg-gray-800 transition"
        >
          Resume
        </a>
      </div>
    </div>
  </header>
</template>

<script setup>
import ThemeToggle from './ThemeToggle.vue'
</script>
