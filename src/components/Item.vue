<template>
  <div class="relative max-w-7xl mx-auto px-6 py-10 sm:px-6 lg:px-0">
    <div class="mx-auto text-base max-w-prose lg:max-w-none">
      <div>
        <h2 class="text-base text-indigo-600 font-semibold tracking-wide uppercase flex items-center">
          <CurrencyDollarIcon class="w-5 h-5 text-indgo-600 mr-1" />
          {{ item.price }}
        </h2>
        <h2 class="text-base text-indigo-600 font-semibold tracking-wide flex items-center">
          <CalendarIcon class="w-5 h-5 text-indgo-600 mr-1" />
          Available: {{ item.pickup }}
        </h2>
        <h3 class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
          {{ item.name }}
        </h3>
      </div>
    </div>
    <div class="mt-8">
      <div class="text-base mx-auto max-w-prose lg:max-w-none">
        <figure class="overflow-x-auto w-full">
          <div class="aspect-none flex previews">
            <img
              v-for="image of images"
              :key="image"
              class="object-cover object-center mr-2" 
              :src="`/img/${image}`" 
              :alt="item.name"
            />
          </div>
        </figure>
      </div>
      <div class="mt-4" v-if="item.description">
        <div class="text-base max-w-prose mx-auto lg:max-w-none">
          <p class="text-md text-gray-500" v-html="item.description" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { CurrencyDollarIcon, CalendarIcon } from '@heroicons/vue/solid'

export default {
  components: {
    CurrencyDollarIcon,
    CalendarIcon
  },
  props: {
    item: Object
  },
  computed: {
    images () {
      return this.item.images && this.item.images.split(',')
    }
  }
}
</script>

<style scoped>
.previews {
  max-width: 500px;
}

@media (max-width: 600px)  {
  .previews {
    max-width: 100%;
    max-height: 300px;
  }
}
</style>