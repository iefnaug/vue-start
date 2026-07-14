<script setup lang="ts">
defineProps(['title', 'post'])
defineEmits(['enlarge-text'])
</script>

<template>
  <h4>{{ title }}</h4>
  <div>{{ post?.content || 'No post content' }}</div>
  <slot/>
  <button @click="$emit('enlarge-text')">Enlarge text</button>
</template>

<style scoped>

</style>