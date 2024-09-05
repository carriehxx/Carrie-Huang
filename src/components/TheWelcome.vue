<script setup>
import photoAlbum from '../components/photoAlbum.vue'

window.addEventListener('scroll', () => {
  const header = document.querySelector('header')
  // header.classList.toggle('sticky', window.scrollY > 0)

  // 获取滚动高度
  const scrollTop = window.scrollY
  // adjusting the image opacity according to the scrolled distance
  const opacity = 1 - scrollTop / window.innerHeight
  header.style.opacity = Math.max(opacity, 0)
})
</script>

<template>
  <header>
    <photoAlbum />

    <div class="greeting">
      <h1>Hi, welcome to my profolio!</h1>
      <p>I'm <span>Carrie Huang</span>, nice to meet you ~</p>
    </div>
  </header>
</template>

<style scoped>
header {
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100vh;
  align-items: left;
  justify-content: center;
  gap: 3rem;
}

.greeting {
  text-align: left;
  font-size: 3rem;
  color: white;
  font-weight: 600;
  padding: 0 2rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;

  font-family: var(--header-font-family);
  font-weight: 1200;
  text-shadow: rgb(255, 255, 242) 0 0 8px;
}

.greeting span {
  color: rgb(206, 250, 180);
}

@media (min-width: 1024px) {
  header {
    display: flex;
    flex-direction: column;
    width: 100vw;
    place-items: center;
    height: 100vh;
  }

  header .wrapper {
    display: flex;
    place-items: center;
    flex-wrap: wrap;
  }

  .greeting {
    text-align: center;
    font-size: 4rem;
  }

  .greeting p {
    font-size: 2rem;
  }
}
</style>
