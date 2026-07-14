<script setup lang="ts">
import {onMounted, useTemplateRef} from "vue";

const input = useTemplateRef<HTMLInputElement>('myInput')
onMounted(() => {
  console.log(input.value)
  input.value?.focus()
})

</script>

<template>
  <input type="text" ref="myInput">
</template>

<style scoped>

</style>