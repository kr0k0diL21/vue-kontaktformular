<script setup lang="ts">
import Sidebar from '@/components/MySidebar.vue'

import { ref } from 'vue'
const name = ref('')
const email = ref('')
const message = ref('')

const submitForm = () => {
  // Prüfen: Alle Felder gefüllt?
  if (!name.value || !email.value || !message.value) {
    alert('Bitte füllen Sie alle Felder aus.')
    return
  }

  // Erfolg
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
  <div class="flex min-h-screen bg-gray-50">
    <!-- Sidebar links -->
    <Sidebar />

    <!-- Hauptbereich rechts -->
    <main class="flex-1 p-8">
      <h1 class="text-3xl font-bold mb-6 text-gray-800">Willkommen im Dashboard</h1>
      <p class="text-gray-600 mb-8">Wähle einen Menüpunkt in der Sidebar aus.</p>

      <!-- Dein Kontaktformular kommt später hier rein -->
      <div class="bg-white p-6 rounded-lg shadow-lg max-w-2xl mx-auto">
    <h2 class="text-2xl font-bold text-gray-800 mb-6">Kontaktieren Sie uns</h2>

    <form @submit.prevent="submitForm" class="space-y-5">
      <!-- Name -->
      <div>
        <label class="block text-sm font-medium text-gray-700 mb-1">Name</label>
        <input
          v-model="name"
          type="text"
          placeholder="Ihr Name"
          required
          class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition"
        />
      </div>

      <!-- E-Mail -->
      <div>
        <label class="block text-sm font-medium text-gray-700 mb-1">E-Mail</label>
        <input
          v-model="email"
          type="email"
          placeholder="Ihre E-Mail"
          required
          class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition"
        />
      </div>

      <!-- Nachricht -->
      <div>
        <label class="block text-sm font-medium text-gray-700 mb-1">Nachricht</label>
        <textarea
          v-model="message"
          rows="5"
          placeholder="Ihre Nachricht..."
          required
          class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent resize-none transition"
        ></textarea>
      </div>

      <!-- Button -->
      <button
        type="submit"
        class="w-full bg-blue-600 text-white py-3 rounded-lg font-semibold hover:bg-blue-700 transition shadow-md"
      >
        Absenden
      </button>
    </form>

    <!-- Live-Vorschau -->
    <div class="mt-8 p-5 bg-gray-50 rounded-lg border border-gray-200">
      <h3 class="text-lg font-semibold text-gray-700 mb-3">Live-Vorschau:</h3>
      <p><strong>Name:</strong> {{ name || '—' }}</p>
      <p><strong>E-Mail:</strong> {{ email || '—' }}</p>
      <p><strong>Nachricht:</strong> {{ message || '—' }}</p>
    </div>
  </div>
    </main>
  </div>
</template>
