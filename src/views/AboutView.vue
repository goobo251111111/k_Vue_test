<script setup>
import { ImgComparisonSlider } from '@img-comparison-slider/vue'
</script>
<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ImgComparisonSlider>
      <img
        slot="first"
        style="width: 100%"
        src="https://img-comparison-slider.sneas.io/demo/images/before.webp"
      />

      <img
        slot="second"
        style="width: 100%"
        src="https://img-comparison-slider.sneas.io/demo/images/after.webp"
      />
      <!-- 2. import imageX from ...
        <img
        slot="second"
        style="width: 100%"
        src="imageX.jpg"
      /> -->
      <!-- 3. public 資料夾
        <img
        slot="second"
        style="width: 100%"
        src="/image/x.jpg"
      /> -->
    </ImgComparisonSlider>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
