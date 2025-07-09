<template>
  <section
    id="home"
    class="relative flex items-center justify-center min-h-screen px-4 bg-animated-dark overflow-hidden"
  >
    <!-- Background Elements -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 left-1/4 w-64 h-64 bg-gradient-to-r from-blue-600/20 to-purple-600/20 rounded-full blur-2xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-gradient-to-r from-purple-600/20 to-pink-600/20 rounded-full blur-2xl"></div>
    </div>

    <div class="relative z-10 max-w-4xl mx-auto text-center">
      <!-- Main Content -->
      <div class="animate-fade-in-up">
        <h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 text-white leading-tight px-4">
        </h1>
        <h2 class="text-xl md:text-3xl lg:text-4xl font-semibold mb-8 text-gray-300 px-4">
          Frontend Web Developer
        </h2>
        
        <p class="text-gray-400 text-base md:text-lg lg:text-xl mb-12 max-w-2xl mx-auto leading-relaxed px-4">
          Not your average developer — I specialize in building modern, responsive web applications. 
          With a background in law and sales, I bring a unique perspective to everything I build.
        </p>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-4 justify-center mb-12 px-4">
          <a
            href="#projects"
            class="btn-primary px-6 sm:px-8 py-3 sm:py-4 rounded-full text-white font-semibold hover:shadow-2xl transition-all duration-300 inline-flex items-center justify-center gap-2"
          >
            View My Work
            <ArrowDown class="w-5 h-5" />
          </a>
          <a
            href="#contact"
            class="px-6 sm:px-8 py-3 sm:py-4 rounded-full border-2 border-white/30 text-white font-semibold hover:bg-white/10 hover:border-white/50 transition-all duration-300 inline-flex items-center justify-center gap-2"
          >
            Get In Touch
            <Mail class="w-5 h-5" />
          </a>
        </div>

        <!-- Social Links -->
        <div class="flex justify-center space-x-4 sm:space-x-6 px-4">
          <a
            v-for="social in socialLinks"
            :key="social.name"
            :href="social.url"
            target="_blank"
            class="group p-3 sm:p-4 rounded-full border border-white/20 hover:border-white/40 hover:bg-white/10 transition-all duration-300 hover:scale-110"
          >
            <component :is="social.icon" class="w-5 h-5 sm:w-6 sm:h-6 text-white/70 group-hover:text-white transition-colors" />
          </a>
        </div>
      </div>

      <!-- Scroll Indicator -->
      <div class="absolute bottom-4 sm:bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
        <div class="w-6 h-10 border-2 border-white/30 rounded-full flex justify-center">
          <div class="w-1 h-3 bg-white/50 rounded-full mt-2 animate-pulse"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Github, Linkedin, Mail, ArrowDown } from 'lucide-vue-next'

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
</script>