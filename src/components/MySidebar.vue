<script setup lang="ts">
import { ref } from 'vue'
import {
  HomeIcon,
  InboxIcon,
  MagnifyingGlassIcon,
  Cog6ToothIcon,
  QuestionMarkCircleIcon,
  SparklesIcon,
  Square2StackIcon,
  TicketIcon,
  MegaphoneIcon,
  ChevronDownIcon,
  // UserIcon, ShieldCheckIcon, LightBulbIcon, ArrowRightStartOnRectangleIcon,  ← entfernt
  PlusIcon,
} from '@heroicons/vue/24/outline'

const isOpen = ref(false)
const userOpen = ref(false) // für später
</script>

<template>
  <aside class="w-64 bg-white border-r border-gray-200 h-screen flex flex-col">
    <!-- Header -->
    <div class="p-4 border-b border-gray-200">
      <div class="flex items-center justify-between cursor-pointer" @click="isOpen = !isOpen">
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-blue-600 rounded-lg flex items-center justify-center text-white font-bold"
          >
            AW
          </div>
          <span class="font-semibold">Artiom Walser</span>
        </div>
        <ChevronDownIcon class="w-5 h-5" :class="{ 'rotate-180': isOpen }" />
      </div>

      <!-- Dropdown -->
      <div v-if="isOpen" class="mt-2 bg-gray-50 rounded-lg p-2">
        <div class="p-2 hover:bg-white rounded cursor-pointer">Workation</div>
        <div class="p-2 hover:bg-white rounded cursor-pointer flex items-center gap-2">
          <PlusIcon class="w-4 h-4" /> New team
        </div>
      </div>
    </div>

    <!-- Suche + Inbox -->
    <div class="p-4 space-y-2">
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <MagnifyingGlassIcon class="w-5 h-5" />
        <span>Search</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <InboxIcon class="w-5 h-5" />
        <span>Inbox</span>
      </a>
    </div>

    <!-- Hauptmenü -->
    <nav class="flex-1 px-4 space-y-1">
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <HomeIcon class="w-5 h-5" />
        <span>Home</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <Square2StackIcon class="w-5 h-5" />
        <span>Events</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <TicketIcon class="w-5 h-5" />
        <span>Orders</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <MegaphoneIcon class="w-5 h-5" />
        <span>Broadcasts</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <Cog6ToothIcon class="w-5 h-5" />
        <span>Settings</span>
      </a>
    </nav>

    <!-- Footer -->
    <div class="p-4 border-t border-gray-200">
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <QuestionMarkCircleIcon class="w-5 h-5" />
        <span>Support</span>
      </a>
      <a href="#" class="flex items-center gap-3 p-2 hover:bg-gray-100 rounded-lg">
        <SparklesIcon class="w-5 h-5" />
        <span>Changelog</span>
      </a>

      <!-- User Dropdown -->
      <div class="mt-4 p-2 hover:bg-gray-100 rounded-lg cursor-pointer">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 bg-gray-300 rounded-full"></div>
          <div>
            <div class="font-medium text-sm">Arti</div>
            <div class="text-xs text-gray-500">arti@example.com</div>
          </div>
          <ChevronDownIcon class="w-5 h-5 ml-auto" />
        </div>
      </div>
    </div>
  </aside>
</template>
