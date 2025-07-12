<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Button from './components/Button.vue'
</script>

<template>
  <Header />
  <main>
    <Button></Button>
    <RouterView />
  </main>
</template>

<style lang="scss" scoped></style>
