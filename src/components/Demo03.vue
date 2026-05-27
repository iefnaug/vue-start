<script setup>
//计算属性
import { reactive, computed } from 'vue';

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})
const message = computed(() => {
  return author.books.length > 0 ? 'yes' : 'no'
})

</script>

<template>
  <h1>计算属性</h1>
  <p>{{message}}</p>
</template>

<style scoped>

</style>