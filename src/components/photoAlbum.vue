<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const images = [
  './assets/photoCollection/photo1.jpg',
  './assets/photoCollection/photo3.jpg',
  './assets/photoCollection/photo4.jpg',
  './assets/photoCollection/photo5.jpg'
]

const currentIdx = ref(0)

let intervalId

onMounted(() => {
  startImageRotation()
})

onUnmounted(() => {
  clearInterval(intervalId)
})

function startImageRotation() {
  intervalId = setInterval(() => {
    currentIdx.value = (currentIdx.value + 1) % images.length
  }, 3000) // 每 3 秒切换一次图像
}
</script>

<template>
  <img
    v-if="images.length"
    :src="images[currentIdx]"
    alt="background image"
    class="img-background"
  />
</template>

<style scoped>
.img-background {
  position: absolute;
  width: 100vw;
  height: 100vh;
  z-index: -1;
  top: 0;
  left: 0;
  background-position: center;
  background-repeat: no-repeat;
  object-fit: cover;
}

@media (min-width: 1024px) {
  .img-background {
    height: 100wh;
  }
}
</style>
