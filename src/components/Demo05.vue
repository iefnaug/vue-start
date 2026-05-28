<script setup>
//条件渲染
import {ref} from "vue";

const show = ref(false)
function showOrHide() {
  show.value = !show.value;
}
</script>

<template>
  <button @click="showOrHide">click me</button>
  <div class="box" v-if="show">1</div>
  <template v-else>
    <div class="box">2</div>
    <div class="box">3</div>
  </template>

  <h1 v-show="true">v-show</h1>

</template>

<style scoped>
.box {
  width: 100px;
  height: 100px;
  background-color: #c084fc;
}
</style>