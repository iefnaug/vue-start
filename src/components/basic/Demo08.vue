<script setup lang="js">
import {reactive, ref, watch, watchEffect} from 'vue'

const question = ref('')
const answer = ref('Questions usually contain a question mark. ;-)')
const loading = ref(false)
const address = ref('')
//watch 可以直接侦听一个 ref
watch(question, async (newQuestion, oldQuestion) => {
  if (newQuestion.includes('?')) {
    loading.value = true
    answer.value = 'Thinking...'
    try {
      const res = await fetch('https://yesno.wtf/api')
      const json = await res.json()
      answer.value = json.answer
      address.value = json.image
    } catch (error) {
      answer.value = 'Error! Could not reach the API. ' + error
    } finally {
      loading.value = false
    }
  }
})

//watch getter函数, 不能直接监听 reactive 对象的属性
const name = ref('gf')
watch(() => name.value, (newName) => {
  console.log(newName)
})

const obj = reactive({count: 0, count2: 0})
watch(() => obj.count, (newCount) => {
  console.log(newCount)
})

//监听 reactive 对象的所有属性变化，谨慎使用
watch(obj, (newObj) => {
  console.log(newObj)
})

//即时回调
const source = ref('map')
watch(() => source.value, (newSource) => {
  console.log(newSource)
}, {immediate: true, once: true})

/**
 * watchEffect
 */
const age = ref(10)
watchEffect(() => {
  console.log(age.value)
})

</script>


<template>
  <p>
    Ask a yes/no question:
    <input v-model="question" :disabled="loading" />
  </p>
  <p>{{ answer }}</p>
  <img :src="address" alt="loading" />
</template>

<style scoped>

</style>