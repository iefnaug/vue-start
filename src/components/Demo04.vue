<script setup>
//类与样式绑定
import {computed, reactive, ref} from 'vue'
const isActive = ref(true)
//响应式
// const multi = reactive({
//   s1: true,
//   s2: true
// })

//计算属性
const multi = computed(() => {
  return {
    s1: Date.now() > 0,
    s2: true
  }
})
</script>

<template>
  <div class="wrapper">
    <!--在原有属性的机上可以叠加-->
    <div class="box" :class="{active: isActive}"></div>
    <div :class="multi"></div>
    <div></div>
  </div>
</template>

<style scoped>
.wrapper {
  height: 100px;
  display: flex;
  flex-direction: row;
  gap: 10px;
}
.wrapper div {
  flex: 1;
  background-color: #c084fc;
}

.wrapper .box {
  border: 2px solid white;
}

.wrapper .s1 {
  border: 2px solid green;
}

.wrapper .s2 {
  border-radius: 50%;
}

.wrapper .active {
  background-color: lightsalmon;
}
</style>