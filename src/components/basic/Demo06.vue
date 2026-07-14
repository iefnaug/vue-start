<script setup>
import {ref} from "vue";

const messages = ref([
  {message: "haha"},
  {message: "haha2"}
])

const obj = ref({
  name: "John",
  age: 30
})

function add() {
  messages.value.push({
    message: "hahaN" + Math.random(),
  })
}

function reset() {
  messages.value = [];
}
</script>

<template>
  <button @click="add">add</button>
  <button @click="reset">reset</button>
  <div>
    <ul>
      <li v-for="(item, index) in messages">{{ index }}: {{ item.message }}</li>
    </ul>

    <ul>
      <li v-for="({message}, index) in messages">{{ index }}: {{ message }}</li>
    </ul>
  </div>

  <div>
    <template v-for="(v, k, idx) in obj" :key="idx">
      <div>
        <span>{{ k }}: {{ v }} : {{ idx }}</span>
      </div>
    </template>
  </div>
</template>

<style scoped>

</style>