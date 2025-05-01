<template>
  <section
    id="contact"
    class="py-20 px-6 bg-white dark:bg-black text-black dark:text-white transition-colors duration-300"
  >
    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-10 items-start">
      <!-- Contact Info -->
      <div>
        <h2 class="text-3xl font-bold mb-4">Contact.</h2>
        <p class="text-lg text-gray-600 dark:text-gray-300 mb-10">
          I'd be happy to connect! Feel free to reach out for project inquiries, collaboration
          opportunities, or any other questions you may have.
        </p>

        <ul class="space-y-6">
          <li class="flex items-center">
            <div
              class="h-10 w-10 flex items-center justify-center rounded bg-blue-600 text-white mr-4"
            >
              <Mail class="w-5 h-5" />
            </div>
            <div>
              <h3 class="font-semibold text-lg">Email</h3>
              <a href="mailto:bbe-operations@outlook.com" class="text-gray-700 dark:text-gray-300">
                bbe-operations@outlook.com
              </a>
            </div>
          </li>

          <li class="flex items-center">
            <div
              class="h-10 w-10 flex items-center justify-center rounded bg-blue-600 text-white mr-4"
            >
              <Linkedin class="w-5 h-5" />
            </div>
            <div>
              <h3 class="font-semibold text-lg">LinkedIn</h3>
              <a
                href="https://www.linkedin.com/in/bunyaminbolukbas/"
                target="_blank"
                class="text-gray-700 dark:text-gray-300"
              >
                @bunyaminbolukbas
              </a>
            </div>
          </li>

          <li class="flex items-center">
            <div
              class="h-10 w-10 flex items-center justify-center rounded bg-blue-600 text-white mr-4"
            >
              <Github class="w-5 h-5" />
            </div>
            <div>
              <h3 class="font-semibold text-lg">GitHub</h3>
              <a
                href="https://github.com/Bunyamin-1058754"
                target="_blank"
                class="text-gray-700 dark:text-gray-300"
              >
                @Bunyamin-1058754
              </a>
            </div>
          </li>
        </ul>
      </div>

      <!-- Contact Form -->
      <div class="bg-white dark:bg-gray-900 p-6 rounded-xl shadow space-y-6">
        <form @submit.prevent="handleSubmit" class="space-y-6">
          <div>
            <label for="email" class="block text-sm font-medium mb-2">Email</label>
            <input
              v-model="form.email"
              type="email"
              id="email"
              name="email"
              required
              class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>

          <div>
            <label for="subject" class="block text-sm font-medium mb-2">Subject</label>
            <input
              v-model="form.subject"
              type="text"
              id="subject"
              name="subject"
              required
              class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>

          <div>
            <label for="message" class="block text-sm font-medium mb-2">Message</label>
            <textarea
              v-model="form.message"
              id="message"
              name="message"
              rows="5"
              required
              class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500"
            ></textarea>
          </div>

          <button
            type="submit"
            :disabled="pending"
            class="w-full bg-blue-600 text-white py-2 rounded-md font-semibold hover:bg-blue-700 transition"
          >
            {{ pending ? 'Sending...' : 'Send Message' }}
          </button>

          <p v-if="message" class="text-center text-green-600 dark:text-green-400 font-medium">
            {{ message }}
          </p>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Mail, Linkedin, Github } from 'lucide-vue-next'

const form = ref({
  email: '',
  subject: '',
  message: '',
})
const pending = ref(false)
const message = ref('')
const endpoint = 'https://formspree.io/f/mnndnple'

async function handleSubmit() {
  pending.value = true
  try {
    const response = await fetch(endpoint, {
      method: 'POST',
      headers: { Accept: 'application/json' },
      body: new FormData(document.querySelector('form')),
    })
    if (response.ok) {
      message.value = "Thank you for your message! I'll get back to you soon."
      form.value = { email: '', subject: '', message: '' }
    } else {
      message.value = 'Something went wrong. Please try again.'
    }
  } catch {
    message.value = 'Something went wrong. Please try again.'
  } finally {
    pending.value = false
  }
}
</script>
