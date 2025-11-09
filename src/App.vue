<script setup lang="ts">
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')

const submitForm = () => {
  if (!name.value || !email.value || !message.value) {
    alert('Bitte füllen Sie alle Felder aus.')
    return
  }

  console.log('Formular gesendet!')
  console.log('Name:', name.value)
  console.log('E-Mail:', email.value)
  console.log('Nachricht:', message.value)

  // Formular leeren
  name.value = ''
  email.value = ''
  message.value = ''
}
</script>

<template>
  <div class="min-h-screen bg-gray-100 p-8">
    <h1 class="text-4xl font-bold text-center mb-8">Kontaktformular</h1>

    <form @submit.prevent="submitForm" class="max-w-md mx-auto bg-white p-6 rounded-lg shadow">
      <div class="mb-4">
        <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
        <input
          v-model="name"
          type="text"
          class="w-full border border-gray-300 p-2 rounded focus:ring-2 focus:ring-blue-500"
          placeholder="Ihr Name"
        />
      </div>

      <div class="mb-4">
        <label class="block text-sm font-medium text-gray-700 mb-1">E-Mail</label>
        <input
          v-model="email"
          type="email"
          class="w-full border border-gray-300 p-2 rounded focus:ring-2 focus:ring-blue-500"
          placeholder="Ihre E-Mail"
        />
      </div>

      <div class="mb-4">
        <label class="block text-sm font-medium text-gray-700 mb-1">Nachricht</label>
        <textarea
          v-model="message"
          class="w-full border border-gray-300 p-2 rounded focus:ring-2 focus:ring-blue-500 resize-none"
          rows="4"
          placeholder="Ihre Nachricht"
        ></textarea>
      </div>

      <button
        type="submit"
        class="w-full bg-blue-500 text-white p-2 rounded hover:bg-blue-600 transition font-medium"
      >
        Senden
      </button>
    </form>

    <!-- LIVE-VORSCHAU -->
    <div class="mt-8 bg-white p-6 rounded-lg shadow max-w-md mx-auto">
      <h2 class="text-2xl font-bold mb-4">Eingereichte Daten</h2>
      <p><strong>Name:</strong> {{ name || '-' }}</p>
      <p><strong>E-Mail:</strong> {{ email || '-' }}</p>
      <p><strong>Nachricht:</strong> {{ message || '-' }}</p>
    </div>
  </div>
</template>
