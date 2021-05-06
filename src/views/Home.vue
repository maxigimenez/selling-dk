<template>
  <div class="bg-white overflow-hidden">
    <Header />
    <div class="pb-10 mb-5">
      <Loader v-if="isLoading" />
      <Item
        v-else
        v-for="item in items"
        :key="item.name"
        :item="item"
      />
    </div>
  </div>
</template>
<script>
import Header from '../components/Header.vue'
import Item from '../components/Item.vue'
import Loader from '../components/Loader.vue'

export default {
  components: { Header, Item, Loader },
  data () {
    return {
      items: [],
      isLoading: true
    }
  },
  async mounted () {
    const response = await fetch('https://sheetapi.co/apis/ryZPQXbYGAtJA1C3yCsfAf/raw?limit=50')
    const data = await response.json()
    this.items = data.filter(item => item.available === 'YES')
    this.isLoading = false
  }
}
</script>