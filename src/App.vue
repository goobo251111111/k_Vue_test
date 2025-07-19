<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Header.vue'
</script>

<template>
  <Header />
  <main>
    <!-- <Button></Button> -->
    <RouterView />
  </main>
</template>

<style lang="scss" scoped></style>
