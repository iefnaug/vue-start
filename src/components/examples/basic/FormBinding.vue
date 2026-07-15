<script setup lang="ts">
import {ref} from "vue";

const text = ref<string>('Edit me')
const checked = ref<boolean>(true)
const checkedNames = ref(['Jack'])
const picked = ref('One')
const selected = ref('A')
const multiSelected = ref(['A'])


</script>

<template>
  <h2>文本</h2>
  <input type="text" v-model="text">
  <p>{{ text }}</p>

  <h2>复选框</h2>
  <input type="checkbox" id="checkbox" v-model="checked">
  <label for="checkbox">Checked: {{ checked }}</label>

  <h2>多个复选框</h2>
  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
  <label for="jack">Jack</label>
  <input type="checkbox" id="john" value="John" v-model="checkedNames">
  <label for="john">John</label>
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
  <label for="mike">Mike</label>
  <p>Checked names: {{ checkedNames }}</p>

  <h2>单选按钮</h2>
  <input type="radio" id="one" value="one" v-model="picked">
  <label for="one">One</label>
  <input type="radio" id="two" value="two" v-model="picked">
  <label for="two">Two</label>
  <p>Picked: {{ picked }}</p>

  <h2>下拉选择</h2>
  <select v-model="selected">
    <option value="" disabled>Please select one</option>
    <option value="AA">A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <p>Selected: {{ selected }}</p>

  <h2>多选下拉选择</h2>
  <select v-model="multiSelected" multiple style="width: 100px">
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
    <option value="D">D</option>
    <option value="E">E</option>
  </select>
  <p>Selected: {{ multiSelected }}</p>
</template>

<style scoped>

</style>