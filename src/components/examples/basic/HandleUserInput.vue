<script setup lang="ts">
import {ref} from "vue";

const message = ref<string>('Hello World')
function reverseMessage() {
  message.value = message.value.split('').reverse().join('')
}
function notify() {
  alert('navigation was prevented!')
}
</script>

<template>
  <!--模板中会自动解包-->
  <h1>{{message}}</h1>
  <!--
     绑定到一个方法/函数。
     这个 @click 语法是 v-on:click 的简写。
   -->
  <button @click="reverseMessage">Reverse Message</button>
  <!--也可以写成内联表达式-->
  <button @click="message += '!'">Append</button>
  <!--阻止默认行为-->
  <a href="https://localhost:8080" @click.prevent="notify">
    A link with e.preventDefault()
  </a>
</template>

<style scoped>
  button, a {
    display: block;
    margin-top: 1em;
  }
</style>