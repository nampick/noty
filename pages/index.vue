<template>
  <div>{{ items }}</div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      items: []
    }
  },
  methods: {
    async getItems () {
      const items = await this.$axios.get('http://localhost:3001/api/items')
      this.items = items.data
      console.log(items)
    }
  },
  mounted () {
    this.getItems()
  }
}
</script>
