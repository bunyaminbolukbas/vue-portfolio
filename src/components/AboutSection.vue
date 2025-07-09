<template>
  <section id="about" class="py-24 px-4 bg-gray-50 dark:bg-zinc-900 transition-colors duration-300">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-black dark:text-white">
          About <span class="text-gradient">Me</span>
        </h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto rounded-full"></div>
      </div>

      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Profile Image -->
        <div class="flex justify-center lg:justify-start">
          <div class="relative group">
            <div class="absolute -inset-4 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full blur opacity-25 group-hover:opacity-40 transition duration-300"></div>
            <img
              :src="profileImg"
              alt="Photo of Bunyamin"
              class="relative w-80 h-80 rounded-full object-top object-cover shadow-2xl hover:scale-105 transition-transform duration-300"
            />
            <div class="absolute -bottom-4 -right-4 w-24 h-24 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center shadow-lg">
              <Code class="w-12 h-12 text-white" />
            </div>
          </div>
        </div>

        <!-- Content -->
        <div class="space-y-8">
          <div class="space-y-6 text-lg leading-relaxed text-gray-600 dark:text-gray-300">
            <p class="animate-fade-in-up">
              Hey there! I'm <span class="font-semibold text-black dark:text-white">Bunyamin</span> — 
              I specialize in frontend development with Vue, React, and TypeScript, but I'm also confident 
              working with backend tools like Python, Flask, and Node.js.
            </p>

            <p class="animate-fade-in-up" style="animation-delay: 0.2s;">
              With a background in law and sales, I bring a unique mix of analytical thinking and 
              communication skills to my work. I'm passionate about building modern, secure, and 
              user-focused applications — especially when it comes to solving real-world problems.
            </p>

            <p class="animate-fade-in-up" style="animation-delay: 0.4s;">
              I'm currently open to new opportunities, so if you're hiring or want to collaborate, 
              shoot me a message!
            </p>
          </div>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-8 pt-8 border-t border-gray-200 dark:border-gray-700">
            <div class="text-center">
              <div class="text-3xl font-bold text-gradient mb-2">3+</div>
              <div class="text-sm text-gray-600 dark:text-gray-400">Years Experience</div>
            </div>
            <div class="text-center">
              <div class="text-3xl font-bold text-gradient mb-2">15+</div>
              <div class="text-sm text-gray-600 dark:text-gray-400">Projects Completed</div>
            </div>
            <div class="text-center">
              <div class="text-3xl font-bold text-gradient mb-2">100%</div>
              <div class="text-sm text-gray-600 dark:text-gray-400">Client Satisfaction</div>
            </div>
          </div>

          <!-- Skills Preview -->
          <div class="flex flex-wrap gap-3 pt-6">
            <span 
              v-for="skill in topSkills" 
              :key="skill"
              class="px-4 py-2 bg-gradient-to-r from-blue-600/10 to-purple-600/10 border border-blue-600/20 rounded-full text-sm font-medium text-blue-700 dark:text-blue-300 hover:scale-105 transition-transform duration-200"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Code } from 'lucide-vue-next'
import profileImg from '@/assets/images/profilepic.png'

const topSkills = ['Vue.js', 'React', 'TypeScript', 'Python', 'Node.js', 'TailwindCSS']
</script>