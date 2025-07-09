<template>
  <footer class="bg-gray-50 dark:bg-zinc-900 border-t border-gray-200 dark:border-gray-700 py-12 px-4 transition-colors duration-300">
    <div class="max-w-7xl mx-auto">
      <!-- Main Footer Content -->
      <div class="grid md:grid-cols-4 gap-8 mb-8">
        <!-- Brand -->
        <div class="md:col-span-2">
          <h3 class="text-2xl font-bold text-gradient mb-4">Bünyamin Bölükbaş</h3>
          <p class="text-gray-600 dark:text-gray-300 mb-6 leading-relaxed max-w-md">
            Frontend developer passionate about creating modern, user-focused web applications. 
            Let's build something amazing together.
          </p>
          <div class="flex space-x-4">
            <a
              v-for="social in socialLinks"
              :key="social.name"
              :href="social.url"
              target="_blank"
              class="w-10 h-10 bg-white dark:bg-gray-800 rounded-full flex items-center justify-center hover:bg-blue-600 hover:text-white dark:hover:bg-blue-600 transition-all duration-300 shadow-md hover:shadow-lg hover:scale-110"
            >
              <component :is="social.icon" class="w-5 h-5" />
            </a>
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h4 class="font-semibold text-gray-900 dark:text-white mb-4">Quick Links</h4>
          <ul class="space-y-2">
            <li v-for="link in quickLinks" :key="link.name">
              <a 
                :href="link.href" 
                class="text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors duration-200"
              >
                {{ link.name }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact Info -->
        <div>
          <h4 class="font-semibold text-gray-900 dark:text-white mb-4">Contact</h4>
          <div class="space-y-3">
            <div class="flex items-center gap-3">
              <Mail class="w-4 h-4 text-blue-600" />
              <a 
                href="mailto:bbe-operations@outlook.com" 
                class="text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors duration-200 text-sm"
              >
                bbe-operations@outlook.com
              </a>
            </div>
            <div class="flex items-center gap-3">
              <MapPin class="w-4 h-4 text-blue-600" />
              <span class="text-gray-600 dark:text-gray-300 text-sm">Netherlands</span>
            </div>
            <div class="flex items-center gap-3">
              <Clock class="w-4 h-4 text-green-500" />
              <span class="text-green-600 dark:text-green-400 text-sm font-medium">Available for work</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Divider -->
      <div class="section-divider mb-8"></div>

      <!-- Bottom Footer -->
      <div class="flex flex-col md:flex-row justify-between items-center gap-4">
        <div class="text-sm text-gray-500 dark:text-gray-400 text-center md:text-left">
          <p>
            © 2025 Bünyamin Bölükbaş — Owner of BBE Operations
          </p>
          <p class="mt-1">
            Chambers of commerce 89397703 · All rights reserved
          </p>
        </div>
        
        <div class="flex items-center gap-4 text-sm text-gray-500 dark:text-gray-400">
          <span>Made with</span>
          <Heart class="w-4 h-4 text-red-500 animate-pulse" />
          <span>and Vue.js</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { Github, Linkedin, Mail, MapPin, Clock, Heart } from 'lucide-vue-next'

const socialLinks = [
  {
    name: 'GitHub',
    url: 'https://github.com/bunyaminbolukbas',
    icon: Github
  },
  {
    name: 'LinkedIn',
    url: 'https://www.linkedin.com/in/bunyaminbolukbas/',
    icon: Linkedin
  },
  {
    name: 'Email',
    url: 'mailto:bbe-operations@outlook.com',
    icon: Mail
  }
]

const quickLinks = [
  { name: 'Home', href: '#home' },
  { name: 'About', href: '#about' },
  { name: 'Projects', href: '#projects' },
  { name: 'Skills', href: '#tech' },
  { name: 'Contact', href: '#contact' }
]
</script>