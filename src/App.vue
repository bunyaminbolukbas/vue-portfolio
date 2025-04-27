<template>
  <div
    class="bg-white dark:bg-black text-black dark:text-white p-8 transition-colors duration-300 min-h-screen"
  >
    <!-- Dit zorgt ervoor dat je hele site de juiste styling & dark mode krijgt -->
    🌗 Toggle me met je knop!

    <!-- Hier laad je de volledige site in -->
    <HomeView />
  </div>
</template>

<script setup>
import HomeView from './views/HomeView.vue'
</script>
