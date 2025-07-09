<template>
  <div class="group hover-lift rounded-2xl overflow-hidden bg-white dark:bg-gray-900 shadow-lg hover:shadow-2xl transition-all duration-300 border border-gray-200 dark:border-gray-700">
    <!-- Image Container -->
    <div class="relative aspect-video overflow-hidden bg-gradient-to-br from-gray-100 to-gray-200 dark:from-gray-800 dark:to-gray-700">
      <img
        :src="image || '/placeholder.svg'"
        :alt="title"
        class="object-cover w-full h-full transition-transform duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      
      <!-- Overlay with link -->
      <div class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
        <a
          :href="link"
          target="_blank"
          class="bg-white/90 dark:bg-black/90 backdrop-blur-sm px-6 py-3 rounded-full font-semibold text-gray-900 dark:text-white hover:bg-white dark:hover:bg-black transition-colors duration-200 flex items-center gap-2"
        >
          <ExternalLink class="w-4 h-4" />
          View Project
        </a>
      </div>
    </div>

    <!-- Content -->
    <div class="p-6">
      <h3 class="text-xl font-bold mb-3 text-gray-900 dark:text-white group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors duration-200">
        {{ title }}
      </h3>

      <p class="text-gray-600 dark:text-gray-300 mb-4 leading-relaxed">
        {{ description }}
      </p>

      <!-- Tags -->
      <div class="flex flex-wrap gap-2 mb-6">
        <span
          v-for="tag in tags"
          :key="tag"
          class="px-3 py-1 bg-gradient-to-r from-blue-50 to-purple-50 dark:from-blue-900/30 dark:to-purple-900/30 text-blue-700 dark:text-blue-300 text-xs font-medium rounded-full border border-blue-200/50 dark:border-blue-700/50 hover:scale-105 transition-transform duration-200"
        >
          {{ tag }}
        </span>
      </div>

      <!-- Footer -->
      <div class="flex items-center justify-between pt-4 border-t border-gray-100 dark:border-gray-800">
        <a
          :href="link"
          target="_blank"
          class="inline-flex items-center gap-2 text-sm font-medium text-blue-600 dark:text-blue-400 hover:text-blue-700 dark:hover:text-blue-300 transition-colors duration-200"
        >
          <Github class="w-4 h-4" />
          View on GitHub
        </a>
        
        <div class="flex items-center gap-1 text-gray-400">
          <Star class="w-4 h-4" />
          <span class="text-xs">Featured</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Github, ExternalLink, Star } from 'lucide-vue-next'

defineProps({
  title: String,
  description: String,
  image: String,
  link: String,
  tags: Array,
})
</script>