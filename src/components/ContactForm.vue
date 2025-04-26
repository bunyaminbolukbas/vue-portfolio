<template>
  <div class="rounded-xl border p-6 shadow-sm bg-white">
    <form @submit.prevent="handleSubmit" class="space-y-4">
      <div>
        <label for="name" class="block text-sm font-medium mb-2">Name</label>
        <input
          id="name"
          v-model="form.name"
          name="name"
          required
          class="w-full rounded-md border px-3 py-2 text-sm"
        />
      </div>

      <div>
        <label for="email" class="block text-sm font-medium mb-2">Email</label>
        <input
          id="email"
          type="email"
          v-model="form.email"
          name="email"
          required
          class="w-full rounded-md border px-3 py-2 text-sm"
        />
      </div>

      <div>
        <label for="message" class="block text-sm font-medium mb-2">Message</label>
        <textarea
          id="message"
          v-model="form.message"
          name="message"
          required
          class="w-full rounded-md border px-3 py-2 text-sm"
        ></textarea>
      </div>

      <button
        type="submit"
        :disabled="pending"
        class="w-full bg-blue-600 text-white rounded-md py-2 hover:bg-blue-700 transition"
      >
        {{ pending ? 'Sending...' : 'Send Message' }}
      </button>

      <p v-if="message" class="text-sm text-center mt-4 text-green-600 font-medium">
        {{ message }}
      </p>
    </form>
  </div>
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

const endpoint = 'https://formspree.io/f/mnndnple'

async function handleSubmit() {
  pending.value = true
  try {
    const response = await fetch(endpoint, {
      method: 'POST',
      headers: {
        Accept: 'application/json',
      },
      body: new FormData(document.querySelector('form')),
    })

    if (response.ok) {
      message.value = 'Thanks, I will contact you within maximum 3 days!'
      form.value = { name: '', email: '', message: '' }
    } else {
      message.value = 'Something went wrong, please try again.'
    }
  } catch {
    message.value = 'Something went wrong, please try again.'
  } finally {
    pending.value = false
  }
}
</script>
