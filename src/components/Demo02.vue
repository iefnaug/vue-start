<script setup>
import { ref, nextTick, reactive } from 'vue';

const counter = ref(0);
function increment() {
  counter.value++
}

const obj = ref({
  nested: {count: 0},
  arr: ['foo', 'bar']
})
async function changeRef() {
  obj.value.nested.count++
  obj.value.arr.push('new')
  //更新不是同步的，需要等待
  await nextTick()
  //DOM已经更新
  console.log('do something...')
}

const v = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})

function changeReactive() {
  v.books[0] = 'Vue1'
}

</script>

<template>
  <div class="box" @click="increment">{{counter}}</div>
  <br>
  <div class="box" @click="changeRef">{{ obj.nested.count }}  {{ obj.arr }}</div>
  <br>
  <div class="box" @click="changeReactive">{{v.name}} {{v.books[0]}}</div>
</template>

<style scoped>
.box {
  width: 500px;
  height: 100px;
  line-height: 100px;
  text-align: center;
  background-color: lightsalmon;
  border-radius: 10%;
  box-shadow: 5px 5px 10px silver;
  cursor: pointer;
}

</style>