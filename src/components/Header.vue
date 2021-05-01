<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-6 py-10 sm:px-6 lg:px-0">
      <div class="lg:flex lg:items-center lg:justify-between">
        <div class="flex-1 min-w-0">
          <h2 class="text-2xl font-bold leading-7 text-white sm:text-3xl sm:truncate">
            🇩🇰 🛒
          </h2>
          <div class="mt-1 flex flex-col sm:flex-row sm:flex-wrap sm:mt-0 sm:space-x-6">
            <div class="mt-2 flex items-center text-sm text-gray-300">
              <LocationMarkerIcon class="flex-shrink-0 mr-1.5 h-5 w-5 text-gray-500" aria-hidden="true" />
              Pick-up near Shopping Fields
            </div>
            <div class="mt-2 flex items-center text-sm text-gray-300">
              <CalendarIcon class="flex-shrink-0 mr-1.5 h-5 w-5 text-gray-500" aria-hidden="true" />
              Pick-up before May 15th
            </div>
          </div>
        </div>
        <div class="mt-5 flex lg:mt-0 lg:ml-4">
          <button @click="phoneVisible = !phoneVisible" type="button" class="inline-flex items-center px-4 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-gray-600 hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-indigo-500">
            <PhoneIcon class="-ml-1 mr-2 h-5 w-5 text-gray-300" aria-hidden="true" />
            Contact
            <span v-show="phoneVisible" class="ml-2">+45 50 25 53 47</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  CalendarIcon,
  LocationMarkerIcon,
  PhoneIcon,
} from '@heroicons/vue/solid'
import { ref }from '@vue/reactivity'
const phoneVisible = ref(false)
</script>