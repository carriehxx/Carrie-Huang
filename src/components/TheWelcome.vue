<script setup>
import photoAlbum from '../components/photoAlbum.vue'

window.addEventListener('scroll', () => {
  const header = document.querySelector('header')
  // header.classList.toggle('sticky', window.scrollY > 0)

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
      <h1>Hi, welcome to my portfolio!</h1>
      <p>I'm <span>Huang Xin</span>, nice to meet you ~</p>
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
  padding: 0 1rem;
}

.greeting {
  text-align: left;
  font-size: 2rem;
  color: white;
  font-weight: 600;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  mix-blend-mode: hard-light;

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
    position: relative;
  }

  .greeting::after {
    content: '';
    width: 150px;
    height: 150px;
    position: absolute;
    background-image: url('./assets/chevrons-down-regular-48.png');
    background-size: cover;
    background-repeat: no-repeat;
    bottom: 10%;
    left: 50%;
    opacity: 0.7;
    color: white;
    animation: bounce 2s infinite;
  }

  @keyframes bounce {
    0%,
    20%,
    50%,
    80%,
    100% {
      transform: translate(-50%, 0);
    }
    40% {
      transform: translate(-50%, -30px);
    }
    60% {
      transform: translate(-50%, -15px);
    }
  }

  .greeting {
    padding: 0 1rem;
    text-align: left;
    font-size: 3.5rem;
  }

  .greeting p {
    font-size: 3rem;
    padding: 0 2rem;
    margin: 0 auto;
    opacity: 0;
    animation: fadeInUp 1s ease-out forwards;
    animation-delay: 1s;
  }

  .greeting h1 {
    padding: 0 2rem;
    margin: 0 auto;
    opacity: 0;
    animation: fadeInUp 1s ease-out forwards;
  }

  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(30px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
}
</style>
