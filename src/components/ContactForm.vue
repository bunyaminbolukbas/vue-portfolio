<template>
  <section
    id="contact"
    class="py-16 px-4 bg-white dark:bg-black text-black dark:text-white transition-colors duration-300"
  >
    <h2 class="text-4xl font-bold text-center mb-8">Get in Touch</h2>

    <div
      class="max-w-2xl mx-auto bg-white dark:bg-gray-900 rounded-xl shadow p-6 transition-colors duration-300"
    >
      <form @submit.prevent="handleSubmit" class="space-y-6">
        <div>
          <label for="name" class="block text-sm font-medium mb-2">Name</label>
          <input
            v-model="form.name"
            type="text"
            id="name"
            name="name"
            required
            class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-black dark:focus:ring-white transition"
          />
        </div>

        <div>
          <label for="email" class="block text-sm font-medium mb-2">Email</label>
          <input
            v-model="form.email"
            type="email"
            id="email"
            name="email"
            required
            class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-black dark:focus:ring-white transition"
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
            class="w-full rounded-md border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 text-black dark:text-white px-4 py-2 shadow-sm focus:outline-none focus:ring-2 focus:ring-black dark:focus:ring-white transition"
          ></textarea>
        </div>

        <button
          type="submit"
          :disabled="pending"
          class="w-full bg-black text-white dark:bg-white dark:text-black py-2 rounded-md font-semibold hover:bg-gray-900 dark:hover:bg-gray-200 transition"
        >
          {{ pending ? 'Sending...' : 'Send Message' }}
        </button>

        <p v-if="message" class="text-center text-green-600 dark:text-green-400 font-medium mt-4">
          {{ message }}
        </p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  message: '',
})
const pending = ref(false)
const message = ref('')
const endpoint = 'https://formspree.io/f/mnndnple' // endpoint for Formspree

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
      form.value = { name: '', email: '', message: '' }
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
