<script setup>
import {ref} from 'vue'
const count = ref(0)
let clazz = 'box'
function clickIt(e) {
  e.target.classList.toggle('box')
  count.value++
  clazz = 'box2';
}

const innerHTML = "<p>a</p><p>b</p>"
</script>

<template>
<div class="wrapper">
  <div @click="(e) => clickIt(e)">{{count}}</div>
  <div v-html="innerHTML"></div>
  <div v-bind:class="clazz">3</div>
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

.wrapper .box2 {
  background-color: bisque;
}
</style>