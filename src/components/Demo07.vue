<script setup>
import { reactive } from "vue";
const user = reactive({
    name: '张三',
    age: 18,
    hobby: ['篮球'],
    city: '北京',
    gender: '男',
});

function submitForm() {
    console.log(user);
    // 在这里处理表单提交逻辑，如发送API请求
}
</script>

<template>
  <div>
    <form @submit.prevent="submitForm">
      <input type="text" v-model="user.name" placeholder="请输入姓名"><br>
      <input type="number" v-model="user.age" placeholder="请输入年龄"><br>
      性别
      <input type="radio" v-model="user.gender" value="男">男
      <input type="radio" v-model="user.gender" value="女">女
      <br>
      爱好
      <input type="checkbox" v-model="user.hobby" value="篮球">篮球
      <input type="checkbox" v-model="user.hobby" value="足球">足球
      <input type="checkbox" v-model="user.hobby" value="跑步">跑步
      <input type="checkbox" v-model="user.hobby" value="其他">其他
      <br>
      城市
      <select v-model="user.city">
        <option value="北京">北京</option>
        <option value="上海">上海</option>
        <option value="广州">广州</option>
        <option value="深圳">深圳</option>
      </select><br>
      <button type="submit">提交</button>
    </form>
  </div>
</template>

<style scoped>
  div {
    background-color: #c084fc;
  }
</style>