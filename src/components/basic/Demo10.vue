<script setup lang="ts">
import ButtonCounter from "./ButtonCounter.vue";
import BlogPost from "./BlogPost.vue";
import {ref} from "vue";

const posts = ref([
  { id: 1, title: 'My journey with Vue', content: 'fun' },
  { id: 2, title: 'Blogging with Vue', content: 'bad story' },
  { id: 3, title: 'Why Vue is so fun', content: 'love' }
])
const postFontSize = ref(1)

const components = [ButtonCounter, BlogPost]
const index = ref(0)
function getIndex() {
  index.value = (index.value + 1) % 2
}
</script>

<template>
  <h1>Button Counter</h1>
  <ButtonCounter/>
  <ButtonCounter/>
  <ButtonCounter/>

  <h1>Article</h1>
  <div :style="{ fontSize: postFontSize + 'em' }">
    <BlogPost v-for="post in posts"
              :key="post.id"
              :title="post.title"
              :post="post"
              @enlarge-text="postFontSize += 0.1">
      插槽
    </BlogPost>
  </div>

  <h1 @click="getIndex">组件切换</h1>
  <component :is="components[index]"></component>
</template>

<style scoped>

</style>