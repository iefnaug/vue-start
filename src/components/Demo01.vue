<script setup>
import {ref} from 'vue'
const count = ref(0)
function clickIt(e) {
  console.log('clickIt')
  e.target.classList.toggle('box')
}
</script>

<template>
<div class="wrapper">
  <div @click="(e) => {clickIt(e); count++}">{{count}}</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
</template>

<style scoped>
.wrapper {
  width: 600px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 100px;
  background-color: #9ca3af;
}

.wrapper div {
  background-color: #c084fc;
}

.wrapper .box {
  background-color: lightcoral;
}
</style>