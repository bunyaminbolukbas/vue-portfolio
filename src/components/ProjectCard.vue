<template>
  <div
    class="rounded-xl border overflow-hidden shadow-sm bg-white dark:bg-gray-900 dark:border-gray-700 transition-colors duration-300"
  >
    <div class="relative aspect-video overflow-hidden">
      <img
        :src="image || '/placeholder.svg'"
        :alt="title"
        class="object-cover w-full h-full transition-transform hover:scale-105"
      />
    </div>

    <div class="p-4">
      <h3 class="text-xl font-semibold mb-2">{{ title }}</h3>

      <p class="text-sm text-gray-600 dark:text-gray-300 mb-4">
        {{ description }}
      </p>

      <div class="flex flex-wrap gap-2 mb-4">
        <span
          v-for="tag in tags"
          :key="tag"
          class="inline-flex items-center rounded-md bg-gray-100 dark:bg-gray-800 text-gray-800 dark:text-gray-200 px-2 py-1 text-xs font-medium ring-1 ring-inset ring-gray-300 dark:ring-gray-600"
        >
          {{ tag }}
        </span>
      </div>

      <a
        :href="link"
        target="_blank"
        class="inline-flex items-center gap-2 text-sm text-blue-600 hover:underline"
      >
        <span class="text-lg">🔗</span>
        View on GitHub
      </a>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  image: String,
  link: String,
  tags: Array,
})
</script>
