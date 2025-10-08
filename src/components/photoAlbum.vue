<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const images = [
  './assets/photoCollection/photo1.jpg',
  './assets/photoCollection/photo3.jpg',
  './assets/photoCollection/photo4.jpg',
  './assets/photoCollection/photo5.jpg'
]

const currentIdx = ref(0)
const imgbg = document.querySelector('.img-background')

let intervalId

onMounted(() => {
  startImageRotation()
  // imgbg.style.animation = "fadeInOut 3s infinite"
})

onUnmounted(() => {
  clearInterval(intervalId)
})

function startImageRotation() {
  intervalId = setInterval(() => {
    currentIdx.value = (currentIdx.value + 1) % images.length
  }, 3000)
}
</script>

<template>
  <div class="img-background"></div>
</template>

<style scoped>
.img-background {
  position: absolute;
  width: 100vw;
  height: 100vh;
  z-index: -1;
  top: 0;
  left: 0;
  background: #0d131a;
}

@keyframes fadeInOut {
  0% {
    opacity: 0;
  }
  10% {
    opacity: .2;
  }
  20% {
    opacity: .4;
  }
  30% {
    opacity: .7;
  }
}

@media (min-width: 1024px) {
  .img-background {
    height: 100wh;
  }
}
</style>
