<script setup>
import { ref, onMounted } from 'vue'
import { fakeProducts } from '@/assets/data/product'

const count = ref(0)
const cart = ref([])

const loadCart = () => {
  const stored = localStorage.getItem('cart')
  // cart.value = stored ? JSON.parse(stored) : []
  const cartIds = stored ? JSON.parse(stored) : []

  const result = fakeProducts.filter((item) => {
    return cartIds.includes(String(item.id))
  })

  cart.value = result
}

const clearCart = () => {
  localStorage.removeItem('cart')
  cart.value = []
}

onMounted(() => {
  count.value = 1
  loadCart()
})
</script>
<template>
  <div class="cart">
    <h1>購物車車</h1>
    <ul>
      <li v-for="item in cart" key="item.id">
        <img :src="item.image" :alt="item.name" />
        <div>
          <p>{{ item.name }}</p>
          <p>{{ item.price }}</p>
        </div>
        <div class="btn">
          <button>-</button>
          <span>1</span>
          <button>+</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<style lang="scss">
ul {
  li {
    display: flex;
    padding: 10px;
    img {
      width: 150px;
      height: auto;
    }
    .btn {
      align-self: flex-end;
      button {
        width: 40px;
        height: 20px;
      }
    }
  }
}
</style>
