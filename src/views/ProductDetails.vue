<script setup>
import { computed } from 'vue'
import { fakeProducts } from '@/assets/data/product'
const props = defineProps(['id'])
const info = computed(() => {
  return fakeProducts.find(() => {
    return item.id === Number(props.id)
  })
})
const addCart = () => {
  1
  const oldCart = localStorage.getItem('cart')
  2
  const newCart = oldCart ? JSON.parse(oldCart) : []
  3
  newCart.push(props.id)
  localStorage.setItem('cart', JSON.stringify(newCart))
  alert(`已加入購物車：商品 ${props.id}`)
}
</script>
<template>
  <div class="productdetails">
    <h1>商品詳情</h1>
    <div>{{ $route.params.id }}</div>
    <div>{{ props.id }}</div>
    <!-- {{ info }} -->
    <button @click="addCart">加入</button>
  </div>
</template>

<style></style>
