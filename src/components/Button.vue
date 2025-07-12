<script setup>
import { ref } from 'vue'
const count = ref(1)
const noise = ref(false)
const shout = ref('ahhhhhhhhhhhhhhhhhhhhhhhh!')

const text = ref('Hola!')
const list = ref(['A', 'B', 'C'])

const addCount = () => {
  count.value++
}

const toggleNoise = () => {
  noise.value = !noise.value
}
</script>

<template>
  <button @click="addCount">{{ count }}</button>

  <button @click="toggleNoise">noise = {{ noise }}</button>

  <p v-if="noise">{{ shout }}</p>
  <p v-else>shh...</p>
  <br>

  <input v-model="text" type="text" />
  <p>{{ text }}</p>

  <ul>
      <li v-for="item in list">{{ item }}</li>
  </ul>

</template>

<style scoped></style>
