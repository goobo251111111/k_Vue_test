<script setup>
import { ref } from 'vue'
const list = ref([
  { title: 'favicon', icon: 'favicon.ico' },
  { title: 'favicon2', icon: 'favicon2.ico' },
  { title: 'favicon3', icon: 'favicon3.ico' },
])
// const parseAssetsIcon = (fileName) => {
//   return new URL(`@/public/${fileName}`, import.meta.url).href
// }
const parsePublicIcon = (fileName) => `${fileName}`
</script>
<template>
  <div class="products">
    <h1>This is an products page</h1>
  </div>
  <div v-for="item in list" :key="item.title">
    <img :src="parsePublicIcon(item.icon)" />
    {{ item.title }}
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .products {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
