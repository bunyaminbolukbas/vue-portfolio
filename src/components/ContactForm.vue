<template>
  <section
    id="contact"
    class="py-24 px-6 bg-white dark:bg-black text-black dark:text-white transition-colors duration-300"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold mb-6">
          Let's <span class="text-gradient">Connect</span>
        </h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto rounded-full mb-6"></div>
        <p class="text-xl text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
          Ready to start your next project? Let's discuss how we can work together to bring your ideas to life.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-16 items-start">
        <!-- Contact Info -->
        <div class="space-y-8">
          <div class="animate-fade-in-left">
            <h3 class="text-2xl font-bold mb-6">Get in Touch</h3>
            <p class="text-lg text-gray-600 dark:text-gray-300 mb-8 leading-relaxed">
              I'd be happy to connect! Feel free to reach out for project inquiries, collaboration
              opportunities, or any other questions you may have.
            </p>
          </div>

          <!-- Contact Methods -->
          <div class="space-y-6">
            <div 
              v-for="(contact, index) in contactMethods" 
              :key="contact.type"
              class="group flex items-center p-6 bg-gray-50 dark:bg-gray-900 rounded-2xl hover:bg-blue-50 dark:hover:bg-blue-900/20 transition-all duration-300 hover-lift animate-fade-in-left"
              :style="{ animationDelay: `${index * 0.1}s` }"
            >
              <div class="flex-shrink-0 w-16 h-16 bg-gradient-to-r from-blue-600 to-purple-600 rounded-2xl flex items-center justify-center mr-6 group-hover:scale-110 transition-transform duration-300">
                <component :is="contact.icon" class="w-8 h-8 text-white" />
              </div>
              <div>
                <h4 class="font-bold text-lg mb-2 group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors duration-200">
                  {{ contact.type }}
                </h4>
                <a 
                  :href="contact.href" 
                  :target="contact.external ? '_blank' : undefined"
                  class="text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors duration-200"
                >
                  {{ contact.value }}
                </a>
              </div>
            </div>
          </div>

          <!-- Availability Status -->
          <div class="p-6 bg-green-50 dark:bg-green-900/20 rounded-2xl border border-green-200 dark:border-green-700/50 animate-fade-in-left" style="animation-delay: 0.4s;">
            <div class="flex items-center gap-3 mb-3">
              <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
              <span class="font-semibold text-green-700 dark:text-green-300">Available for Work</span>
            </div>
            <p class="text-green-600 dark:text-green-400 text-sm">
              Currently accepting new projects and collaboration opportunities
            </p>
          </div>
        </div>

        <!-- Contact Form -->
        <div class="animate-fade-in-right">
          <div class="bg-gray-50 dark:bg-gray-900 p-8 rounded-2xl shadow-lg border border-gray-200 dark:border-gray-700">
            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div class="grid md:grid-cols-2 gap-6">
                <div>
                  <label for="name" class="block text-sm font-semibold mb-3 text-gray-700 dark:text-gray-300">
                    Full Name
                  </label>
                  <input
                    v-model="form.name"
                    type="text"
                    id="name"
                    name="name"
                    required
                    class="w-full rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-3 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-200"
                    placeholder="Your full name"
                  />
                </div>

                <div>
                  <label for="email" class="block text-sm font-semibold mb-3 text-gray-700 dark:text-gray-300">
                    Email Address
                  </label>
                  <input
                    v-model="form.email"
                    type="email"
                    id="email"
                    name="email"
                    required
                    class="w-full rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-3 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-200"
                    placeholder="your.email@example.com"
                  />
                </div>
              </div>

              <div>
                <label for="subject" class="block text-sm font-semibold mb-3 text-gray-700 dark:text-gray-300">
                  Subject
                </label>
                <input
                  v-model="form.subject"
                  type="text"
                  id="subject"
                  name="subject"
                  required
                  class="w-full rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-3 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-200"
                  placeholder="What's this about?"
                />
              </div>

              <div>
                <label for="message" class="block text-sm font-semibold mb-3 text-gray-700 dark:text-gray-300">
                  Message
                </label>
                <textarea
                  v-model="form.message"
                  id="message"
                  name="message"
                  rows="6"
                  required
                  class="w-full rounded-xl border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-3 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-200 resize-none"
                  placeholder="Tell me about your project or inquiry..."
                ></textarea>
              </div>

              <button
                type="submit"
                :disabled="pending"
                class="w-full btn-primary py-4 rounded-xl font-semibold text-white transition-all duration-300 disabled:opacity-50 disabled:cursor-not-allowed flex items-center justify-center gap-3"
              >
                <Send class="w-5 h-5" />
                {{ pending ? 'Sending...' : 'Send Message' }}
              </button>

              <div v-if="message" class="text-center p-4 rounded-xl" :class="messageType === 'success' ? 'bg-green-50 dark:bg-green-900/20 text-green-600 dark:text-green-400' : 'bg-red-50 dark:bg-red-900/20 text-red-600 dark:text-red-400'">
                <div class="flex items-center justify-center gap-2">
                  <CheckCircle v-if="messageType === 'success'" class="w-5 h-5" />
                  <AlertCircle v-else class="w-5 h-5" />
                  <span class="font-medium">{{ message }}</span>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Mail, Linkedin, Github, Send, CheckCircle, AlertCircle } from 'lucide-vue-next'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})
const pending = ref(false)
const message = ref('')
const messageType = ref('success')
const endpoint = 'https://formspree.io/f/mnndnple'

const contactMethods = [
  {
    type: 'Email',
    value: 'bbe-operations@outlook.com',
    href: 'mailto:bbe-operations@outlook.com',
    icon: Mail,
    external: false
  },
  {
    type: 'LinkedIn',
    value: '@bunyaminbolukbas',
    href: 'https://www.linkedin.com/in/bunyaminbolukbas/',
    icon: Linkedin,
    external: true
  },
  {
    type: 'GitHub',
    value: '@bunyaminbolukbas',
    href: 'https://github.com/bunyaminbolukbas',
    icon: Github,
    external: true
  }
]

async function handleSubmit() {
  pending.value = true
  message.value = ''
  
  try {
    const response = await fetch(endpoint, {
      method: 'POST',
      headers: { Accept: 'application/json' },
      body: new FormData(document.querySelector('form')),
    })
    
    if (response.ok) {
      messageType.value = 'success'
      message.value = "Thank you for your message! I'll get back to you soon."
      form.value = { name: '', email: '', subject: '', message: '' }
    } else {
      messageType.value = 'error'
      message.value = 'Something went wrong. Please try again or contact me directly.'
    }
  } catch {
    messageType.value = 'error'
    message.value = 'Something went wrong. Please try again or contact me directly.'
  } finally {
    pending.value = false
  }
}
</script>