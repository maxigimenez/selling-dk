<template>
  <div class="bg-white overflow-hidden">
    <Item
      v-for="item in items"
      :key="item.name"
      :item="item"
    />
  </div>
</template>
<script>
import Item from '../components/Item.vue'

export default {
  components: { Item },
  data () {
    return {
      items: []
    }
  },
  async mounted () {
    const response = await fetch('https://sheetapi.co/apis/ryZPQXbYGAtJA1C3yCsfAf/raw')
    const data = await response.json()
    this.items = data.filter(item => item.available === 'YES')
  }
}
</script>