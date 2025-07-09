<template>
  <header
    class="fixed top-0 z-50 w-full transition-all duration-300"
    :class="[
      scrolled 
        ? 'bg-white/90 dark:bg-black/90 backdrop-blur-md shadow-lg border-b border-gray-200/50 dark:border-gray-700/50' 
        : 'bg-transparent'
    ]"
  >
    <div class="container mx-auto flex h-16 items-center justify-between px-6">
      <!-- Logo/Name -->
      <div class="font-bold text-xl tracking-tight text-gradient animate-fade-in-left">
        Bünyamin Bölükbaş
      </div>

      <!-- Desktop Navigation -->
      <nav class="hidden md:flex space-x-8 text-sm font-medium animate-fade-in-right">
        <a 
          v-for="item in navItems" 
          :key="item.href"
          :href="item.href" 
          class="relative text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors duration-300 group"
        >
          {{ item.label }}
          <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-gradient-to-r from-blue-600 to-purple-600 transition-all duration-300 group-hover:w-full"></span>
        </a>
      </nav>

      <!-- Mobile Menu Button -->
      <button 
        @click="toggleMobileMenu"
        class="md:hidden p-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors"
      >
        <div class="w-6 h-6 flex flex-col justify-center items-center">
          <span 
            class="w-5 h-0.5 bg-current transition-all duration-300"
            :class="mobileMenuOpen ? 'rotate-45 translate-y-0.5' : ''"
          ></span>
          <span 
            class="w-5 h-0.5 bg-current mt-1 transition-all duration-300"
            :class="mobileMenuOpen ? 'opacity-0' : ''"
          ></span>
          <span 
            class="w-5 h-0.5 bg-current mt-1 transition-all duration-300"
            :class="mobileMenuOpen ? '-rotate-45 -translate-y-1.5' : ''"
          ></span>
        </div>
      </button>
    </div>

    <!-- Mobile Menu -->
    <div 
      class="md:hidden transition-all duration-300 overflow-hidden"
      :class="mobileMenuOpen ? 'max-h-64 opacity-100' : 'max-h-0 opacity-0'"
    >
      <nav class="px-6 py-4 bg-white/95 dark:bg-black/95 backdrop-blur-md border-t border-gray-200/50 dark:border-gray-700/50">
        <a 
          v-for="item in navItems" 
          :key="item.href"
          :href="item.href" 
          @click="closeMobileMenu"
          class="block py-2 text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors"
        >
          {{ item.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileMenuOpen = ref(false)

const navItems = [
  { href: '#home', label: 'Home' },
  { href: '#about', label: 'About' },
  { href: '#projects', label: 'Projects' },
  { href: '#tech', label: 'Skills' },
  { href: '#contact', label: 'Contact' }
]

const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>