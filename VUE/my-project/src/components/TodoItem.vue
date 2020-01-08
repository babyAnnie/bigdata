<template>
  <li @click="handleDelete" class="item">
    {{content}}
  </li>
</template>

<script>
export default {
  props: ['content', 'index'],
  methods: {
    handleDelete () {
      this.$emit('deleteItem', this.index)
    }
  }
}
</script>

<style scoped>
.item{
  color: green
}
</style>
