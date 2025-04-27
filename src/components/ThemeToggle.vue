<template>
  <button
    @click="toggleTheme"
    class="ml-2 rounded-md border px-3 py-1 text-sm font-medium hover:bg-gray-100 dark:hover:bg-gray-700 transition"
  >
    {{ isDark ? '🌙' : '☀️' }}
  </button>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

onMounted(() => {
  isDark.value = document.documentElement.classList.contains('dark')
})

function toggleTheme() {
  isDark.value = !isDark.value
  document.documentElement.classList.toggle('dark', isDark.value)
  console.log('CURRENT CLASSES:', document.documentElement.classList.value)
}
</script>
